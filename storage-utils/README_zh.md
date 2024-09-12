## 功能

该扩展组件包含多个存储相关的实用工具：

- snapshot-controller: 用于为 PVC 创建快照。
- snapshotclass-controller: 用于为快照计数。
- pvc-auto-resizer: 用于为 PVC 在容量不足的情况下实现自动扩容。
- storageclass-accessor: 提供准入控制器，用来验证是否准许在某个项目或企业空间创建 PVC。

### 限制

`pvc-auto-resizer` 需要连接 Prometheus 服务才能工作。

如果您在安装 storage-utils（KubeSphere 存储）扩展组件之后，才安装 Prometheus 服务，或更改了之前的 Prometheus 服务，需要重启 storage-utils 的工作负载，才能使 pvc-auto-resizer 正常工作：

```
kubectl -n extension-storage-utils rollout restart deployment storage-utils
```

## 安装

1. 通过 **扩展市场** 页面找到 **KubeSphere 存储** 扩展组件，点击 **安装**，选择最新版本，点击 **下一步** 按钮；
2. 在 **扩展组件安装** 标签页面中，根据需求点击并修改 **扩展组件配置**，配置完成后，点击 **开始安装** 按钮，开始安装；
3. 安装完成后，点击 **下一步** 按钮，进入集群选择页面，勾选需要安装的集群，点击 **下一步** 按钮，进入 **差异化配置** 页面；
4. 根据需求更新 **差异化配置**，更新完成，开始安装，静待安装完成。

## 快速开始

安装完成后，可在以下页面使用该扩展组件提供的功能：

- 集群左侧导航栏的**存储**菜单下将显⽰**卷快照**和**卷快照类**；**存储**菜单下的**存储类**将显示**设置授权规则**和**设置自动扩展**操作项。
- 项目左侧导航栏的**存储**菜单下将显⽰**卷快照**。

> 通常情况下，集群节点的本地存储系统不支持卷快照和卷扩展功能。您需要为 KubeSphere 集群安装存储插件，确保后端存储系统支持卷快照和卷扩展功能。有关更多信息，请联系您的存储系统提供商。

### 存储类

在集群左侧导航栏的**存储**菜单下的**存储类**详情页面，点击**更多操作** > **设置授权规则**/**设置自动扩展**。

- 设置授权规则：用户只能在特定项目和企业空间使用存储类。

- 设置自动扩展：系统在卷剩余空间低于阈值时自动扩展卷容量。

> 请确保后端存储系统支持卷扩展功能，且存储类已启用卷扩展功能。操作方法：存储类 > 更多操作 > 设置卷操作 > 启用卷扩展。


### 卷快照类

卷快照类用于定义卷快照的存储类型。在集群的**卷快照类**菜单下，可创建、查看、编辑卷快照类。

> 创建卷快照类前，请确保后端存储系统支持卷快照功能。

### 卷快照

卷快照保存了存储卷的当前数据，可用于创建持久卷声明以及对应的持久卷。卷快照创建后，系统将在后端存储系统中保存快照数据。

> 创建卷快照前，请确保后端存储系统支持卷快照功能，并已在持久卷声明对应的存储类上启用卷快照功能。操作方法：存储类 > 更多操作 > 设置卷操作 > 启用卷快照创建。
> 
> 创建卷快照前，请确保已创建卷快照类。

在集群的**卷快照**菜单下，可为持久卷声明创建卷快照，使用卷快照创建持久卷，查看、编辑卷快照内容。

在项目的**卷快照**菜单下，可为持久卷声明创建卷快照，使用卷快照创建持久卷。


## 卸载

通过 **扩展市场** 页面找到 **KubeSphere 存储**，选择已安装的版本，点击 **卸载** 按钮，开始卸载。