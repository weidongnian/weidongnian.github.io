### abp vnext api host 项目中未启用Aauth2认证，需要手动开启

1. **引用nuget包**

    dotnet add package Swashbuckle.AspNetCore.Filters
    
2. **在api host的启动类(启动abpmodel)里加入swagger代码**

           context.Services.AddSwaggerGen (
                options =>
                {
                    options.OperationFilter<AddResponseHeadersFilter>();
                    options.OperationFilter<AppendAuthorizeToSummaryOperationFilter>();
                    options.OperationFilter<SecurityRequirementsOperationFilter>();
                    
                    options.AddSecurityDefinition("oauth2", new OpenApiSecurityScheme
                    {
                        Description = "JWT授权(数据将在请求头中进行传输) 直接在下框中输入Bearer {token}（注意两者之间是一个空格）\"",
                        Name = "Authorization",//jwt默认的参数名称
                        In = ParameterLocation.Header,//jwt默认存放Authorization信息的位置(请求头中)
                        Type = SecuritySchemeType.ApiKey
                    });
                    
                    options.SwaggerDoc ("v1", new OpenApiInfo { Title = "Api中心", Version = "v1" });
                    
                    options.DocInclusionPredicate ((docName, description) => true);
                });
                
3. **运行接口(站点)，会发现swagger ui首页，右上角上有一个Authorize按钮，点击后弹出输入框，请输入identity4登录返回来的token，然后可以在线调试需要认证的接口了**
     
     
