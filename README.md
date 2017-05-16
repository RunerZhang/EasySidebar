# EasySidebar

最近项目已经收尾 想自己造一个侧边抽屉栏的轮子 功能非常简单 后续会继续完善

效果图如下

![](https://github.com/RunerZhang/EasySidebar/blob/master/Untitled.gif)

> 其中用到了 RTRootNavigationController 可以单独设置导航栏 
 https://github.com/rickytan/RTRootNavigationController 
 
 
主要功能代码在``` MenuViewController.m ```

摘录出主要代码
>  将两个视图添加到 MenuViewController
```
    [self addChildViewController:self.leftVC];
    [self.view addSubview:self.leftVC.view];
    self.leftVC.leftDeleate = self;//抽屉视图代理执行跳转功能
    [self addChildViewController:self.baseVC];
    [self.view addSubview:self.baseVC.view];
```
   
   
> 改变主视图位置
``` 
   if(!_isMenuOpen){
            self.baseVC.view.transform = CGAffineTransformMakeTranslation(180, 0);
            self.baseVC.view.transform = CGAffineTransformScale(self.baseVC.view.transform, 0.8, 0.8);
        }
        else {
            self.baseVC.view.transform = CGAffineTransformMakeTranslation(0, 0);
        }
```

