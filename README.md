cron-fix
========

因为1分钟一次的免费Cron实在太难找，云监控频率又普遍比较低，所以写了这货。它会在前四次执行的时候记录下执行时间，计算出Cron的执行间隔，然后从第五次开始在Cron执行的间隔中依靠自身的循环对Cron进行补充。

简单来说，它会把任意频率的Cron修正到1分钟一次。

测试中使用监控宝15分钟一次和30分钟一次的监控都运行良好，执行时间记录显示执行频率接近标准的1分钟一次。

使用方法是把它改名xcron.php【其它也行啦，别和cron文件重名就好了】，和需要执行的cron.php放在一个目录下，然后把云监控的目标设置为xcron.php。
