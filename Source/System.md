# 基础功能

### GCD定时器
```
let queue = DispatchQueue(label: "com.apm.sla")
let timer = DispatchSource.makeTimerSource(flags: [], queue: queue)
timer.schedule(deadline: .now(), repeating: DispatchTimeInterval.seconds(1))
timer.setEventHandler { [weak self] in

}
// 定时器启动
timer.resume()
```
