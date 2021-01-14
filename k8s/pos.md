# pod

> https://kubernetes.io/zh/docs/tasks/configure-pod-container/attach-handler-lifecycle-event/
>
> https://kubernetes.io/zh/docs/concepts/containers/container-lifecycle-hooks/
>
> https://jimmysong.io/kubernetes-handbook/concepts/pod-lifecycle.html

## 生命周期

> ![](/assets/pod-lifecyle.png)

## golang 优雅退出

> ```
> c := make(chan os.Signal)
> 	signal.Notify(c, syscall.SIGHUP)
> 	go func() {
> 		<- c
> 		pluginsCtx.Release()
> 		logger.GetLogger(context.TODO()).Infof("分手也要体面!")
> 	}()
> ```



