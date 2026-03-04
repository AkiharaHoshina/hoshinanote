# NetworkManager 常用命令与含义整理

## 1. `nmcli device`
列出所有网络设备及其状态（已管理/未管理、已连接/未连接）。

## 2. `nmcli c up 4g`
将名为 **4g** 的 NetworkManager 连接配置（connection profile）启动并连接。

- `c` 是 `connection` 的缩写  
- `up` 表示激活该连接

## 3. `nmcli c add type gsm ifname "cdc-wdm3" con-name 4g apn cmnet`
创建一个新的 **GSM/4G 移动网络连接**。

参数说明：

| 参数 | 含义 |
|------|------|
| `type gsm` | 创建 GSM/4G/3G 移动网络连接 |
| `ifname "cdc-wdm3"` | 指定使用的调制解调器接口（通常是 Quectel/MBIM/QMI 设备） |
| `con-name 4g` | 设置连接名称为 4g |
| `apn cmnet` | 设置 APN 为 cmnet（中国移动常用 APN） |

## 4. `nmcli connection delete 4g`
删除名为 **4g** 的连接配置。

## 5. `sudo systemctl restart NetworkManager`
重启 NetworkManager 服务，使配置生效或解决网络异常。

## 6. `ip route get 8.8.8.8`
查询系统访问 **8.8.8.8**（Google DNS）时会使用的路由路径。

常用于：

- 判断当前默认路由走哪张网卡  
- 检查 4G 是否成功成为默认出口  
3
