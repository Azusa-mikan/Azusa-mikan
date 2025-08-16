## 🔹 虚拟机管理常用命令（`virsh`）

| 命令 | 作用 |
| ------------------------------------ | ------------------ |
| `virsh list --all` | 查看所有虚拟机（包含关机的） |
| `virsh list` | 查看正在运行的虚拟机 |
| `virsh start <vmname>` | 启动虚拟机 |
| `virsh shutdown <vmname>` | 发送 ACPI 关机信号（优雅关机） |
| `virsh reboot <vmname>` | 发送 ACPI 重启信号 |
| `virsh destroy <vmname>` | **强制关机**（相当于拔电源） |
| `virsh autostart <vmname>` | 设置虚拟机开机自启动 |
| `virsh autostart --disable <vmname>` | 取消开机自启动 |
| `virsh undefine <vmname>` | 删除虚拟机配置（磁盘文件不会删除） |
| `virsh suspend <vmname>` | 挂起虚拟机 |
| `virsh resume <vmname>` | 恢复挂起的虚拟机 |

---

## 🔹 配置与硬件

| 命令 | 作用 |
| ----------------------------------------------------------------------------- | ------------ |
| `virsh edit <vmname>` | 编辑虚拟机 XML 配置 |
| `virsh dumpxml <vmname>` | 输出虚拟机的完整配置 |
| `virsh attach-disk <vmname> /path/to/disk.img vdb --persistent` | 给虚拟机添加虚拟磁盘 |
| `virsh detach-disk <vmname> vdb --persistent` | 移除虚拟机磁盘 |
| `virsh attach-interface <vmname> network default --model virtio --persistent` | 给虚拟机添加网卡 |
| `virsh detach-interface <vmname> bridge br0 --persistent` | 移除虚拟机网卡 |

---

## 🔹 监控与调试

| 命令 | 作用 |
| ------------------------------- | ------------------------ |
| `virsh console <vmname>` | 连接虚拟机串口控制台（退出用 `Ctrl+]`） |
| `virsh dominfo <vmname>` | 查看虚拟机基本信息 |
| `virsh domblklist <vmname>` | 查看虚拟机的磁盘列表 |
| `virsh domiflist <vmname>` | 查看虚拟机的网卡列表 |
| `virsh domblkinfo <vmname> vda` | 查看某块磁盘的大小信息 |
| `virsh domifaddr <vmname>` | 查看虚拟机获取的 IP 地址 |

---

## 🔹 镜像与快照

| 命令 | 作用 |
| ------------------------------------------------------------------- | ------- |
| `virsh snapshot-create-as <vmname> snap1 "snapshot before upgrade"` | 创建快照 |
| `virsh snapshot-list <vmname>` | 列出虚拟机快照 |
| `virsh snapshot-revert <vmname> snap1` | 回滚到指定快照 |
| `virsh snapshot-delete <vmname> snap1` | 删除快照 |

---

## 🔹 存储池与卷（可选）

| 命令 | 作用 |
| --------------------------------------------------------------- | --------- |
| `virsh pool-list --all` | 查看存储池 |
| `virsh vol-list <poolname>` | 查看存储池里的卷 |
| `virsh vol-create-as <poolname> disk2.qcow2 20G --format qcow2` | 在存储池里创建新卷 |

---
