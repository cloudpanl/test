---

title: Hello Minikube
redirect_from:
- "/docs/hellonode/"
- "/docs/hellonode.html"
---

{% capture overview %}

<!-- 
The goal of this tutorial is for you to turn a simple Hello World Node.js app
into an application running on Kubernetes. The tutorial shows you how to
take code that you have developed on your machine, turn it into a Docker
container image and then run that image on [Minikube](/docs/getting-started-guides/minikube).
Minikube provides a simple way of running Kubernetes on your local machine for free.
-->

本教程的目标是让您将简单的 Hello World Node.js 应用程序转换为在 Kubernetes 上运行的应用程序。 
本教程将向您展示如何使用您在计算机上开发的代码，将其转换为 Docker 容器映像，然后在 [Minikube](/docs/getting-started-guides/minikube) 上运行该映像。
Minikube 提供了一种在您的本地机器上免费运行 Kubernetes 的简单方法。

{% endcapture %}

{% capture objectives %}

<!-- 
* Run a hello world Node.js application.
* Deploy the application to Minikube.
* View application logs.
* Update the application image.
-->

* 运行一个 hello world Node.js 应用程序。
* 将应用程序部署到 Minikube。
* 查看应用程序日志。
* 更新应用程序镜像。

{% endcapture %}

{% capture prerequisites %}

<!-- 
* For OS X, you need [Homebrew](https://brew.sh) to install the `xhyve`
driver.

* [NodeJS](https://nodejs.org/en/) is required to run the sample application.

* Install Docker. On OS X, we recommend
[Docker for Mac](https://docs.docker.com/engine/installation/mac/).
-->

* 对于 OS X, 您需要 [Homebrew](https://brew.sh) 来安装 `xhyve` 驱动程序。

* [NodeJS](https://nodejs.org/en/) 需要运行示例应用程序。

* 安装 Docker. 在 OS X 上, 我们推荐 [Docker for Mac](https://docs.docker.com/engine/installation/mac/)。

{% endcapture %}

{% capture lessoncontent %}

<!-- 
## Create a Minikube cluster

This tutorial uses [Minikube](https://github.com/kubernetes/minikube) to
create a local cluster. This tutorial also assumes you are using
[Docker for Mac](https://docs.docker.com/engine/installation/mac/)
on OS X. If you are on a different platform like Linux, or using VirtualBox
instead of Docker for Mac, the instructions to install Minikube may be
slightly different. For general Minikube installation instructions, see
the [Minikube installation guide](/docs/getting-started-guides/minikube/).

Use `curl` to download and install the latest Minikube release:
-->

## 创建 Minikube 集群

本教程使用 [Minikube](https://github.com/kubernetes/minikube) 创建本地群集。 
本教程还假设您在 OS X 上使用 [Docker for Mac](https://docs.docker.com/engine/installation/mac/)。
如果你在一个不同的平台，像 Linux ，或使用 VirtualBox 而不是 Docker for Mac,安装 Minikube 的指令可能略有不同。 
有关 Minikube 的安装说明，请参阅 [Minikube 安装指南](/docs/getting-started-guides/minikube/)。


使用 `curl` 下载并安装最新的 Minikube 版本：

```shell
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && \
  chmod +x minikube && \
  sudo mv minikube /usr/local/bin/
```
