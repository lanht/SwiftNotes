# 开发QA
## xxx moudlue not found
经常Pod导入第三方，用模拟器build的话会有这个这个报错，可能是一些库不支持模拟器arm64导致
一般会在pod的下如下代码：
```
post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings["EXCLUDED_ARCHS[sdk=iphonesimulator*]"] = "arm64"
        end
    end
end
```
这事要同时在项目的build setting的 excluded architectures 的 `debug` 和 `release` 修改 Any iOS Simulator SDK 为 arm64




