# A good method for interface integration between front-end  developer and back-end developer

# 背景

在前后联调过程中，经常会出现的对话情景是：

前端：我传的参数和请求的URL是对的,为啥404或者返回为空或返回不正确？

后端：我本地是好的，你是怎么传参的？

前端：balabala说半天,发截图，发邮件

由于前后端工作语言、开发平台、异地等原因，双方信息不对称或者只是站在自己的角度去理解接口，非常浪费时间和影响联调效率。

# 解决办法

那么此时双方应该用统一的沟通工具，推荐postman, 将双方postman对应的curl code拿出来比对，结果一目了然。

手写curl code也是可以的, 但是没有利用工具方便。

如果后端swagger上有curl code也是可以使用的，但没有postman有存储历史测试脚本的功能。

# 如何生成 curl code

![Image text](https://github.com/liangzhifeng/postman/blob/master/img/1.jpeg)

![Image text](https://github.com/liangzhifeng/postman/blob/master/img/2.jpeg)

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

双方可以很容易通过 复制 -> 粘贴 -> 运行 -> 复现或比对curl code的差异来解决问题。
