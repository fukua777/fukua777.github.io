---
title: About　axios
categories: 甫夸之谈———JS
tags: "vue"
---

> 关于

　　Axios是一个基于promise的HTTP库，可以用在浏览器和node.js中，主要特征：
+ 从浏览器中创建XHR
+ 从node.js中创建http
+ 支持Promise
+ 自动转换JSON数据
+ 转换请求数据和响应数据
<!-- more -->
+ 拦截请求和响应
+ 取消请求
+ 客户端支持防御XSRF

> 主要方法别名

+ axios.request(config)
+ axios.get(url[,config])
+ axios.delete(url[,config])
+ axios.head(url[,config])
+ axios.post(url[,data[,config]])
+ axios.put(url[,data[,config]])
+ axios.patch(url[,data[,config]])

> 配置

　　```
        {
            url: '',
            method: '',     //默认是get
            baseURL: '',
            transformRequest: [function(){
                //在发送请求之前对数据进行处理，只能用在POST/PUT/PATCH
            }],
            transformResponse: [function(){
                //在响应数据传给then/catch之前对数据进行处理
            }],
            headers: {},
            params: {
                //与URL一起发送的请求参数
            },
            paramsSerializer: function(){
                //对params进行序列化
            },
            data: {
                //请求主体，只能用在POST/PUT/PATCH
            },
            timeout: 1000,
            withCredentials: false      //跨域请求时是否需要使用凭证，默认false
            adapter: function(){
                //允许自定义处理请求，返回一个promise
            },
            auth: {
                username: '',
                password: '',       //表示应该使用HTTP基础验证，并提供Authorization头，会覆写headers设置的Authorization头
            },
            responseType: 'json',       //响应类型，默认json
            xsrfCookieName: 'XSRF-TOKEN',       //xsrf token的cookie的名称
            xsrfHeaderName: 'X-XSRF-TOKEN',     //承载xsrf token的Http头的名称
            onUploadProgress: function(){},
            onUploadProgress: function(){},
            maxContentLength: 2000,
            validateStatus: function(status){
                return status >= 200 && status < 300;       //默认，指定promise是resolve还是reject
            },
            maxRedirects: 5,        //默认，定义在node.js中follow的最大重定向数目
            httpAgent: new http.Agent({ keepAlive: true }),     //在node.js中用于定义在执行http和https时使用的自定义代理,默认不启用
            httpsAgent: new https.Agent({ keepAlive: true }),
            proxy: {
                host: '',
                port: 8888,
                auth: {
                    username: '',
                    password: ''
                }
            },
            cancelToken: new CancelToken(function (cancel) {
                //取消请求的cancel token
            })
        }
　　```

> 其它

+ ``axios.defaults.attr = ''``;     //全局默认值
+ ``var instance = axios.create({key: value});``        //创建实例
+ ``instance.defaults.headers.common['attr'] = ''``     //实例创建后修改默认值
+ ``axios.interceptors.request.use(function(){})``      //请求拦截器
+ ``axios.interceptors.response.use(function(){})``      //响应拦截器
+ ``axios.interceptors.request.eject(myInterceptor);``      //移除拦截器
+ ``axios.all()``       //处理并发请求
+ ``axios.spread(cb)``     
+ axios默认对data采用application/json的方式，要采用application/x-www-urlencoded形式，需要用qs.stringfy(qs方式)或$.params(jq)方式对data进行处理