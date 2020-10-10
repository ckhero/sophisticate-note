# pprof

> [https://segmentfault.com/a/1190000016412013](https://segmentfault.com/a/1190000016412013)

## 常用

> go test -bench=. -cpuprofile=cpu.prof
>
> go tool pprof -http=:6060 cpu.prof
>
> go test -bench=. -memprofile=mem.prof
>
> go tool pprof -http=:6060 mem.prof
>
> go tool pprof http://localhost:6060/debug/pprof/profile   //web



