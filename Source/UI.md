# UI部分

## 1、布局
### 1.1 安全区域顶部和底部
```
let safeTop = UIApplication.shared.keyWindow?.safeAreaInsets.top ?? 0
let safeBottom = UIApplication.shared.keyWindow?.safeAreaInsets.bottom ?? 0
```
### 1.2 导航栏显示与隐藏设置
https://juejin.cn/post/6995836060391440414

## 2、控件
### 2.1 自定义Tabbar样式
```
tabBar.backgroundImage = UIImage()
if #available(iOS 13.0, *) { //去掉分割线
    let appearance = UITabBarAppearance()
    appearance.shadowColor = .clear
    appearance.shadowImage = UIImage()
    appearance.backgroundColor = .clear
    appearance.backgroundImage = UIImage()
    appearance.backgroundImageContentMode = .scaleAspectFill
    self.tabBar.standardAppearance = appearance
    if #available(iOS 15.0, *) {
        self.tabBar.scrollEdgeAppearance = appearance
    }
} else {
    tabBar.shadowImage =  UIImage()
    tabBar.backgroundColor = .clear
}
tabBar.isOpaque = false
```
### 2.2 自定义导航栏样式
```
navigationBar.shadowImage = UIImage()
navigationBar.barTintColor = .white
navigationBar.titleTextAttributes = [NSAttributedString.Key.font: UIFont.systemFont(ofSize: 10)]

if #available(iOS 13.0, *) {
    let navigationBar = UINavigationBar.appearance()

    let appearance = UINavigationBarAppearance()
    appearance.shadowColor = .clear
    appearance.backgroundColor = .white
    appearance.titleTextAttributes = [NSAttributedString.Key.font: UIFont.systemFont(ofSize: 10)]
    navigationBar.scrollEdgeAppearance = appearance
    navigationBar.standardAppearance = appearance
}
```
ps： UITabBarAppearance
> UIBarAppearance是ios13之后苹果新出来的一个类，可以统一配置navigation bars、tab bars、 toolbars等bars的外观。

UIBarAppearance的子类主要有:

+ UITabBarAppearance
+ UINavigationBarAppearance

详情参考：https://www.jianshu.com/p/8b37428bab92
