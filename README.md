# 使用yapi进行自动化测试(笔记)
    https://hellosean1025.github.io/yapi/documents/case.html
    git -> https://github.com/YMFE/yapi

## 前提
    已部署自己的yapi网站         

### a.【接口列表】处录入接口
   ![image](./img/api-add.png)
    
    *. 前端Payload数据对应yapi参数类型为raw,同时 Content-Type=application/json
   ![image](./img/payload-data-1.png)
   ![image](./img/payload-data-2.png) 
  
    *. 前端form-data数据对应yapi参数类型为form,同时 Content-Type=application/x-www-form-urlencoded
   ![img](./img/form-data-1.png)
   ![img](./img/form-data-2.png) 

   *. 前端Query String Parameters数据对应yapi参数类型为Query
   ![img](./img/query-string-param-1.png)
   ![img](./img/query-string-param-2.png) 
    
### b.【测试集合】处添加集合,并导入【接口列表】录入的接口
   ![image](./img/api-test-group.png) 
    
    *.动态url及动态变量配置
        在测试集合中,使用已完成接口的response数据:token,列表集合id作为url对应{id}
   ![image](./img/dynamic-url-1.png)
   ![image](./img/dynamic-param.png)
   ![image](./img/dynamic-param-2.png)
   ![image](./img/dynamic-param-3.png)
    
    *.请求body参数添加动态参数
      eg: "token":  "{{ $.key.body.access_token}}" -> "token":  "{{ $.368.body.access_token}}"
    ![image](./img/yapi-body-dynamic-param.png)   


### c.导出测试报告
    在【测试集合】处点击【服务端测试】在弹框处复制地址，并在浏览器打开
    https://yapi.xxx.com/api/open/run_auto_test?id=39&token=4acc10e4817f81ae8e8128258072dfb007007b28f79bcb9fb6d3e80b1f7d536b&mode=html&email=false&download=false
    将download参数值改为true即可下载
   ![image](./img/export-test-report-1.png)
   ![image](./img/export-test-report-2.png)
   ![image](./img/export-test-report-3.png)
   ![image](./img/export-test-report-4.png) 
