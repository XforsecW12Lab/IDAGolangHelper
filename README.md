> forked from https://github.com/sibears/IDAGolangHelper
> 修改部分文件升级支持python3 可用于idaPro v7.4 以上

## 食用方式
- 解压后放入`IDA根目录\plugins`中,注意保留目录结构。
  - 或者放在随便的一个地方之后使用IDA快捷键`Alt+F7`加载脚本文件，选择`go_entry.py`文件
- 之后会弹出一个GoLoader对话框，可以选择版本等等![image](https://user-images.githubusercontent.com/49470951/110726407-4a479100-8254-11eb-8527-668857e9a203.png)
- 前两个`Try……`用于通过不同的方式自动尝试识别Go版本
- `Rename functions` 是主按键用于触发符号的修复
- `Go version` 用于选择Go版本,大于`1.10`的直接选择`1.10`即可。
- `Add standard go types` 用于增加Go中的复杂标准结构体。
- `Parse types by moduledata` 用于通过moduledata尝试分析类型并修改。

## 大概原理
- 插件使用特征码查找隐藏的或者包含的`.gopclntab`段，并使用其结构恢复符号表
- windows下虽然没有`.gopclntab`段，但是通过特征码`FB FF FF FF 00 00 01 04`依旧可以在`.data`段找到与`.gopclntab`段相同的结构内容
- 请注意`00 00 01 04`可能会更改![Uploading image.png…]()

== 在rename的过程中可能时间有点久，等等就好。之后要点击ok哦 ==

介绍可以看我们的微信公众号：![扫码_搜索联合传播样式-标准色版](https://user-images.githubusercontent.com/49470951/110085246-d9bff080-7dcb-11eb-9e04-da24a26bd6e2.png)
