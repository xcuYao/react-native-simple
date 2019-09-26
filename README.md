# react-native-simple
RN 使用远程pod集成

## 文件说明

0.60.4 📁 对应react-natice [0.60.4](https://github.com/facebook/react-native/releases/tag/v0.60.4) 版本  
0.61.0-rc.0 📁 对应react-natice [0.61.0-rc.0](https://github.com/facebook/react-native/releases/tag/v0.61.0-rc.0) 版本
0.61.0 📁 对应react-natice [0.61.0](https://github.com/facebook/react-native/tree/v0.61.0) 版本

## 使用说明
在Podfile中增加如下源和依赖
```
source 'https://github.com/xcuYao/PrivatePods.git'
source 'https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git'

pod 'RNFramework', '0.1.1'
```
⚠️0.1.0(rn 0.60.4)不支持use_framework!  
🐙0.1.1(rn 0.61.0-rc.0)支持
🐙0.1.2(rn 0.61.0)支持

对于常规的react-native项目 我们一般需要在iOS项目的Podfile中增加类似一堆依赖
```
  pod 'FBLazyVector', :path => "../node_modules/react-native/Libraries/FBLazyVector"
  pod 'FBReactNativeSpec', :path => "../node_modules/react-native/Libraries/FBReactNativeSpec"
  pod 'RCTRequired', :path => "../node_modules/react-native/Libraries/RCTRequired"
  pod 'RCTTypeSafety', :path => "../node_modules/react-native/Libraries/TypeSafety"
  pod 'React', :path => '../node_modules/react-native/'
  pod 'React-Core', :path => '../node_modules/react-native/'
  ...
```

从本地的目录(一般为上级node_modules/react-native)中读取依赖  
这个项目将依赖(podspec)拆到远端[私有源](https://github.com/xcuYao/PrivatePods)  
并封装在[RNFramewrok](https://github.com/xcuYao/PrivatePods/blob/master/RNFramework/0.1.2/RNFramework.podspec)中 这样就解耦了依赖  
方便集成项目，而且公共部分也方便统一处理，新老项目也可快速接入  

具体使用参考示例工程

## 其他
0.60.4版本不支持use_framework!
0.61.0-rc.0已解决
具体可以参考[讨论](https://github.com/facebook/react-native/issues/25349)，[官方说明](https://github.com/facebook/react-native/releases)
