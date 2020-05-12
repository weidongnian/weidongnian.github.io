## abp vnext 新增后台作业监听rabbitMQ的事件总线发来的队列消息

1. **引入依赖到Module**

        [DependsOn (
              typeof(AbpBackgroundWorkersModule)//后台作业
          )]
          public class 项目ApiHostModule : AbpModule {
            //启用后台任务
                Configure<AbpBackgroundWorkerOptions> (options => {
                    options.IsEnabled = true;
                });
          }
  
2. **定义MyBackgroundWorker类，并继承IBackgroundWorker接口**

                namespace SZYJ.Stroke
                {
                    public class TimeEquipmentBackgroundWorker : IBackgroundWorker
                    {
                        private readonly IDistributedEventBus _distributedEventBus;
                        public TimeEquipmentBackgroundWorker(IDistributedEventBus distributedEventBus)
                        {
                            _distributedEventBus=distributedEventBus;
                        }

                        public Task StartAsync(CancellationToken cancellationToken = new CancellationToken())
                        {
                            //作业开始调用
                            _distributedEventBus.Subscribe<事件总线的事件类(含有EventName特性)>(a =>
                            {
                                return Task.Run(() =>
                                {

                                });
                            });

                            return Task.CompletedTask;
                        }

                        public Task StopAsync(CancellationToken cancellationToken = new CancellationToken())
                        {
                            //作业结束调用
                            return Task.CompletedTask;
                        }
                    }
                }
  
3. **定义领域服务(可选)，MyTBackgroundWorkerManager**

              public class MyTBackgroundWorkerManager:IBackgroundWorkerManager
              {
                  private IBackgroundWorker _backgroundWorker;

                  public void Add(IBackgroundWorker worker)
                  {
                      _backgroundWorker = worker;
                  }

                  public Task StartAsync(CancellationToken cancellationToken = new CancellationToken())
                  {
                      return _backgroundWorker.StartAsync(cancellationToken);
                  }

                  public Task StopAsync(CancellationToken cancellationToken = new CancellationToken())
                  {
                      return _backgroundWorker.StopAsync(cancellationToken);
                  }
              }
  
 4. **在Module里的OnApplicationInitialization方法里调用并传入作业类**
 
          public override void OnApplicationInitialization (ApplicationInitializationContext context) {

            context.AddBackgroundWorker<MyBackgroundWorker>();        

          }
 
 
