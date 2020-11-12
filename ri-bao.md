2020-11-08 

1 评审管理后台需求

2 调研定时任务

3 完成定时任务基础架构搭建

明日

1 数据统计接口

1 



统计维度\[DEFAULT:总账户;MERCHANT:商户维度;SHOP:店铺;STAFF:店员;\]







今日

1 解决与前端交互uint64的问题

2 梳理管理后台首页dashboard

3 定时任务统计加盟商日维度的加盟商新增

明日

1 定时任务加盟商日维度的门店，会员，粉丝新增

1 dashborad 管理后台的接口



TOKEN=$\(kubectl -n kube-system describe secret default\| awk '$1=="token:"{print $2}'\)

kubectl config set-credentials docker-desktop --token="${TOKEN}"

echo $TOKEN



kubectl create secret docker-registry regcred -n rebat

2020-11-11

1. 定时任务加盟商日维度的门店，会员，粉丝新增 数据统计

2. 新增购买会员卡通知用户系统逻辑，用于计算新增未购卡用户数据

3 梳理后台加盟商逻辑

明日

1 整理加盟商门店接口

