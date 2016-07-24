Docker Client的创建
Docker Client的创建，实质上是Docker用户通过可执行文件docker，与Docker Server建立联系的客户端。以下分三个小节分别阐述Docker Client的创建流程。

入口：/cmd/docker/docker.go

处理flag信息并收集Docker Client的配置信息

Docker Client的创建其实就是在已有配置参数信息的情况，通过Client包中的NewDockerCli方法创建一个实例cli

可以具体参见./api/client/cli.go。

Docker Client解析请求命令的工作，在Docker命令执行部分第一个完成，直接进入main函数之后的源码部分：
func (cli *Cli) Run(args ...string)

