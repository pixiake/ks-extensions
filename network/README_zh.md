## 功能

这是一个基于 Calico 的 IPPool 和 NetworkPolicy 的 UI 管理界面。它允许用户通过一个友好的用户界面来管理和配置 Calico 的 IPPool 和 NetworkPolicy。

- IPPool 管理：支持创建、更新和删除 IPPools。此外，用户还可以查看每个 IPPool 的详细信息，包括其 CIDR、是否禁用 NAT 等。
- NetworkPolicy 管理：支持创建、更新和删除 NetworkPolicies。此外，用户还可以查看每个 NetworkPolicy 的详细信息，包括其选择器、规则等。

## 安装

1. 通过 **扩展市场** 页面找到 **KubeSphere 网络** 扩展组件，点击 **安装**，选择最新版本，点击 **下一步** 按钮；
2. 在 **扩展组件安装** 标签页面中，根据需求点击并修改 **扩展组件配置**，配置完成后，点击 **开始安装** 按钮，开始安装；
3. 安装完成后，点击 **下一步** 按钮，进入集群选择页面，勾选需要安装的集群，点击 **下一步** 按钮，进入 **差异化配置** 页面；
4. 根据需求更新 **差异化配置**，更新完成，开始安装，静待安装完成。

## 快速开始

安装完成后，可在以下页面使用该扩展组件提供的功能：

- 集群左侧导航栏的**网络**菜单下将显⽰**网络策略**和**容器组 IP 池**；
- 企业空间左侧导航栏的**基本信息**页面将支持启用企业空间网络隔离；
- 项目左侧导航栏的**项目设置**菜单下将显⽰**网络隔离**；
- 创建工作负载或任务时，**高级设置**页签将显示**容器组 IP 池**选项。

### 网络策略

网络策略用于控制集群中容器组的访问和被访问权限，允许在同个集群内实现网络的隔离。您可以使用网络策略实现以下目的：只允许容器组访问特定的其他容器组或网段；只允许容器组被特定的其他容器组或网段访问。

在集群的**网络策略**菜单下，可创建、查看、编辑网络策略。

网络隔离用于控制企业空间和项目中容器组的出站和入站流量。

在企业空间的**基本信息**页面，可启用企业空间网络隔离。启用后，会自动在相应集群中为该企业空间下的所有项目创建网络策略。在项目的**项目设置**菜单下，可启用项目网络隔离，以及添加和删除隔离白名单。启用项目网络隔离会自动在相应集群中为该项目创建网络策略。

### 容器组 IP 池

容器组 IP 池用于为容器组分配 IP 地址。每个容器组 IP 池包含一个可在集群内部访问的私网 IP 网段。

在集群的**容器组 IP 池**菜单下，可创建、查看、编辑、禁用和启用容器组 IP 池，将容器组 IP 池分配到项目，编辑 Overlay 模式，为容器组 IP 池自动匹配合适的节点等。

创建工作负载或任务时，在**高级设置**页签的**容器组 IP 池**选项，可指定容器组 IP 池。这将为工作负载或任务创建的容器组分配此容器组 IP 池中的 IP 地址。


## 卸载

通过 **扩展市场** 页面找到 **KubeSphere 网络**，选择已安装的版本，点击 **卸载** 按钮，开始卸载。