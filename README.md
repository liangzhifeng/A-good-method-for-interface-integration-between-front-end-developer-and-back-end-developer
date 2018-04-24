# postman

# 背景

在前后联调过程中，经常会出现的对话情景是：

前端：我传的参数和请求的URL是对的

后端：我本地是好的

由于前后端工作语言、开发平台、异地等原因，很难去核查谁对谁错的，如果来回断点调试会非常浪费时间和影响联调效率

那么此时双方应该用统一的沟通工具，推荐postman,将各自postman对应的curl code拿出来比对，结果一目了然。

# 如何生成 curl code






得到 curl code 代码如下：

        curl -X POST \
          http://httpbin.org/post \
          -H 'Cache-Control: no-cache' \
          -H 'Content-Type: application/json' \
          -H 'Postman-Token: a2389d58-da17-9b16-961c-d3ae0dcbd35b' \
          -d '{
         "K1": "V1",
         "K2": 2
        }'

其他人可以很容易通过 复制 -> 粘贴 -> 运行 -> 复现 了解该问题！
