# 工厂

## 资料

> [https://www.jianshu.com/p/70f7fd47f2e2](https://www.jianshu.com/p/70f7fd47f2e2)

## 工厂和抽象工厂的区别

> * 工厂和产品一对一，新增产品要新增一个工厂
>
> 抽象工厂和产品1对多，新增产品只需要对工厂做扩展
>
> * 工厂模式利用继承，抽象工厂利用组合
> * 工厂利用子类创造对象，抽象工厂利用接口

```
public function getInfoConfirmUrl($applyCode, $url)
    {
        $apply = Apply::findByApplyCode($applyCode);
        if (empty($apply) || $apply->apply_status !== ApplyConst::APPLY_CHANNEL_COMMIT) {
            throw new UserFixException(Error::ERROR_SYSTEM_ERROR, '订单不存在或者订单不是待确认状态');
        }
        if ($apply->getLoanChannel() == ApplyTransactionConst::LOAN_CHANNEL_YIXIN_HUIMIN) {
            return 'yixin-confirm-info';
        }
        if (in_array($apply->getLoanChannel(), [ApplyTransactionConst::LOAN_CHANNEL_XINGCHEN, ApplyTransactionConst::LOAN_CHANNEL_XINGCHEN_ZX])) {
            return 'xingchen-confirm-info';
        }
        return $apply->isPreChannelConfirm() ? 'preloan-commit': (new BizService())->getUserCheckPage($apply, $url);
    }
```



