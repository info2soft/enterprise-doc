![](/assets/i2-logo.png)

# 英方股份i2UP\(统一数据管理平台\)使用手册

### V7.2

Information2 Software i2UP Manual

### 上海英方软件股份有限公司

![](/assets/qrcode2.png)

# 目录

* [i2灾备软件用户使用手册](README.md) 
* [软件概览](introduction/introduction.md)
  * [系统架构](introduction/system_architecture.md)
  * [核心功能](introduction/core_functions.md)
  * [通信矩阵及端口说明](introduction/ports.md)
* [安装部署](installation/README.md)
  * [节点\(i2Node\)安装](installation/node_install.md)
  * [控制机\(i2CtrlCenter\)安装](installation/ctrl_install.md)
  * [软件卸载](installation/soft_uninstall.md)
* [初始化配置](initialize/initialization_configuration.md)
* [系统设置](system_management/README.md)
  * [用户](system_management/user.md)
    * [用户管理](system_management/user_management.md)
    * [角色管理](system_management/role_management.md)
    * [密钥管理](system_management/accesskey_management.md)
  * [系统参数](system_management/sys_settings.md)
  * [节点在线升级](system_management/upgrade_node.md)
  * [许可管理](system_management/license_management.md)
  * [配置备份](system_management/cc_backup_restore.md)
  * [操作日志](system_management/log_management.md)
* [平台监控](up_monitor/README.md)
  * [平台监控](up_monitor/up_monitor.md)
* [资源管理](resource_management/README.md)
  * [业务组管理](resource_management/groupmanagement.md)
  * [节点管理](resource_management/node_mangement.md)
  * [节点监控](resource_management/node_monitor.md)
  * [文件认证机制](resource_management/file_authentication_mechanism.md)
  * [集群管理](mscs/README.md)
  * [存储管理](resource_management/storage_management.md)
  * [虚拟平台](virtual_platform/add_vp.md)
* [模板管理](template_management/README.md)
  * [虚机备份模板](template_management/vp_backup_temp.md)
  * [虚机复制模板](template_management/vp_rep_temp.md)
  * [全服务备份模板](template_management/fsp_backup_temp.md)
  * [全服务还原模板](template_management/fsp_restore_temp.md)
  * [备份模板](template_management/backup_temp.md)
  * [复制规则模板](template_management/rep_temp.md)
* [规则管理](coopy_cdp/README.md)
  * [创建复制规则](coopy_cdp/new_rep.md)
  * [复制规则高级属性](coopy_cdp/advance_settings.md)
  * [恢复管理](coopy_cdp/recovery_management.md)
* [应用高可用（High Availability）](i2availability/README.md)
  * [添加应用高可用规则](i2availability/new_ha_rep.md)
  * [应用高可用规则列表](i2availability/ha_management.md)
  * [服务器池](i2availability/ha_cls_pool.md)
  * [标签](i2availability/ha_service_label.md)
* [NAS同步规则](coopy_cdp/nas_sync.md)
* [全服务器保护](full_server_protected/README.md)
  * [全服务器迁移](full_server_protected/move.md)
  * [全服务器备份](full_server_protected/backup.md)
  * [全服务器还原](full_server_protected/restore.md)
* [虚拟化支持（i2vp）](virtual_platform/README.md)
  * [NpServer部署](virtual_platform/install_npsvr.md)
  * [虚机备份](virtual_platform/vm_backup.md)
  * [虚机迁移](virtual_platform/vm_move.md)
  * [虚机恢复](virtual_platform/vm_restore.md)
  * [虚机复制](virtual_platform/vm_rep.md)
* [定时管理（i2Backup）](i2backup/README.md)
  * [备份](i2backup/backup.md)
    * [文件备份](i2backup/backup_file.md)
    * [块设备备份](i2backup/backup_blk.md)
    * [oracle备份](i2backup/backup_oracle.md)
    * [mssql server备份](i2backup/backup_mssql.md)
  * [还原](i2backup/restore.md)
* [统计报表](statistics/README.md)
  * [备份统计](statistics/backup.md)
* [实用工具（Utilities）](utilities/README.md)
  * [诊断](utilities/diagnosis.md)
  * [比较与同步](utilities/consistency_comparison.md)
* [消息中心](notification/README.md)
  * [消息通知](notification/message.md)
  * [消息接收管理](notification/messageManagement.md)
* [技术支持](others/technical_support.md)
* [附录](appendix/README.md)
  * [常见错误排查](appendix/troubleshooting.md)
  * [英方软件错误代码说明](appendix/error_code.md)
  * [工作机（生产机）数据变化量诊断工具](appendix/command_tools.md)
  * [升级错误代码说明](appendix/error_code_upgrade.md)
  * [数据库转换](appendix/db_convert.md)




