#腾讯移动端x5内核调试教程
#####背景说明：由于所在公司（酷划在线），年前安卓同学将app内核改为x5，前端组调试页面遇到痛点，看官方说明还是有点不够清晰，经过@李庆美 大哥指点，也加上自己踩过的坑，整理如下希望帮到有需要的小伙伴们。

###步骤：
  1. 在手机安装tbs工具集 4f7aee5881dab314b5b84f00c404eaaf.apk
  2.  将 tbs_20151019_100828_inspector.apk 拷贝到 手机/sdcard/tbs/com.tencent.mm/   目录下（如果tbs下没有com.tencent.mm文件夹，需要手动创建）
  3.  启动微信，在微信任意对话窗口，输入 http://debugtbs.qq.com 发送给任意对象（目的：测试），点击该链接，点击页面中“安装本地tbs内核”
  4.  等待20秒左右，提示安装成功。（失败，请重复上一步）
  5.  在微信中任意对话框，输入任意可访问链接，发送给任意对象，点击该链接
  6.  待页面加载完毕后，打开手机中已安装的tbs工具集软件。点击  “tbs信息查询” 下的 “com.tencent.mm”，如果提示tbs version：88888888 成功，否则请结束微信进程，跳回到第五步的操作。
  7.  电脑进入到附件中，sq_webview_debug/inspector_client20150401（需解压） 文件夹下，执行命令 python ./inspector.py, 命令行展示 ('Serving HTTP on', '0.0.0.0', 'port', 9223, '…') 说明成功。
   8. 保证此时微信中已经在访问有效页面，在chrome浏览器输入 localhost:9222,可以看到下图类似页面说明可以调试