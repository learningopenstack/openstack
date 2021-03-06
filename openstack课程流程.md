# openstack入门 #

## openstack组件相关概念及应用介绍，安装部署 ##

- OpenStack 现场演示
- 详细介绍OpenStack涉及到的概念，并结合实际应用场景介绍相关概念的应用。
- 基本概念：Tenant、User和Role
- 高级概念：Region、AZ、Cell、Host Aggregate
- 如何结合实际应用场景来对应OpenStack中的概念
- 手动OpenStack安装配置step by step 
- Openstack部署架构讲解（3个VM）
- Keystone搭建
- Glance搭建
- Neutron搭建
- Nova搭建
- Dashboard 搭建
- Swift搭建
- Cinder搭建
- 采用OVS + VLAN的组合，实际动手部署OpenStack，给出单节点或多节点手动部署的详细步骤，并演示和介绍自动化部署工具DevStack和PackStack的使用，通过源码深入理解自动化部署的原理，纠正手动部署比自动化部署理解更深的错误认识。
- Openstack 自动化部署方式比较
- DevStack自动化部署原理，并演示单节点和多节点自动化安装部署 
- Fuel OpenStack多节点自动化部署介绍
- PackStack多节点自动化部署介绍
- Puppet 方式部署介绍

## keystone、glance组件 ##

### OpenStack认证组件Keystone ### 

- Keystone介绍和基本概念
- Keystone架构
- Keystone处理流程
- Keystone实验

### OpenStack镜像组件Glance ### 

- Glance介绍和基本概念
- Glance架构
- Glance实验
- 镜像的制作、修改、转换


### openstack 对象存储swift和块存储cinder ### 

- Swift的架构和原理
- Swift的企业部署方案
- Cinder架构
- 基于Cinder的解决方案


## Neutron，Nova组件 ##

### openstack 网络组件Neutron ###

- 网络基础知识
- 网络方案选择
- Neutron组件架构
- OpenStack&SDN网络现状

### OpenStack计算组件Nova ###

- 虚拟化技术KVM,VMWARE,XEN介绍
- Nova介绍及框架
- Nova运行流程
- Nova部署模式
- 虚拟机监控
- Live migrate
- Backup

## openstack HA部署，日志，性能调优 ##

### OpenStack HA方案的选择及日志 ###

- 各组件HA方案
- 日志分析与排除

### 性能瓶颈 ###

- OpenStack平台性能瓶颈
- 虚拟机性能瓶颈

### 性能调优 ###

- OpenStack平台性能调优
- KVM性能调优
- Host OS性能调优


## openstack Dashboard使用 ##

- OpenStack使用
- 命令行操作
- Dashboard操作

## openstack 开发入门 ##

## nova源码架构介绍 ##
- 源码的获取
- 开发环境的搭建
- nova模块调用介绍
- nova源码模块功能介绍
##	添加Nova-api自定义模块 ##
##	数据库表结构的扩展     ##
- nova表结构的扩展
- keystone表结构的扩展
- resetful接口服务的扩展
##	nova数据库调用接口服务的扩展 ##
- compute接口的扩展
- keystone接口服务的扩展
- 基于openstack服务、配置架构自定义服务模块

## Horizon开发之Django ##
- Demo for a "Hello World"
- Django ORM 介绍
- Django Template介绍
- Django View 介绍
## Dashboard源码介绍 ##
- horizon代码模块介绍
- 中文化的功能实现
- 页面按钮的添加
- 列表中下拉菜单的添加
- 列表中文字链接的添加

## openstack 项目实战与经验分享 ##

### OpenStack大规模部署碰到的常见问题及其优化方法 ###
### OpenStack大规模部署案例及经验介绍 ###
- 公有云经验分享
- 私有云经验分享
### OpenStack云平台与其它几种云平台的比较（OpenStack, CloudStack, OpenNebula，VMWare） ###
- 几种主流的开源云平台技术比较
- 几种主流云平台的生态系统比较
### 国内外OpenStack云计算的案例和现状 ###
