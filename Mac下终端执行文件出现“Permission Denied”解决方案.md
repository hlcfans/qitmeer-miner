Mac下终端执行文件出现“Permission Denied”解决方案:

先执行下面这一句

```bash
chmod a+x ./文件名
```

然后再正常执行文件就可以了

例如:
```bash
chmod a+x ./BuildIOS.sh

./BuildIOS.sh
```
就可以了


————————————————
版权声明：本文为CSDN博主「Yu______________」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/yu__jiaoshou/article/details/82149861
