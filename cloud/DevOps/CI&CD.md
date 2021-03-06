# 1. DevOps概念

  DevOps 一词是 Development 和 Operations 的组合，它没有一个固定的词义，在我看来，它是一种框架、方法论，而非一项技术工具。它的出现是为了促进开发、技术运营和质量保障部门之间的沟通、协作与整合，重视开发人员和运维人员之间的沟通协作，通过自动化流程来使得软件构建、测试、发布更加快捷、频繁和可靠。它涵盖一系列的基本原则和实践，其核心价值在于以下两点：

更快速地交付, 响应市场的变化。
更多的关注业务的改进和提升。
  
PS：大白话：多动脑，自动化；多沟通，少动手。

  

2. DevOps作用

## 2.1 产品迭代

在现实生活中，多数用户往往不知道自己想要什么，但是当我们设计出一款产品后，他会告诉我们他不需要什么，这样我们的产品就需要反复的迭代，不断的接近用户的一个渴望值，这个不断迭代的过程肯定是比较曲折的，那我们有什么好的办法快速的交付价值，灵活的响应变化呢？答案就是 DevOps。因为 DevOps 是面向业务目标，助力业务成功的最佳实践。

## 2.2 技术革新

现在的 IT 技术架构随着系统的复杂化不断的革新，从早期的所有服务在一个系统中，发展到现在的微服务架构，从纯手动操作到半自动全自动流程，从单台物理机到云服务平台，这些可以称得上是DevOps的进化史。
  

## 2.3 DevOps技术栈

### 2.3.1 敏捷管理工具

Trello
Teambition
Worktile
Tower

### 2.3.2 产品 & 质量管理工具

Confluence
禅道
Jira
Bugzila

### 2.3.3 代码仓库管理工具

Git
Gitlab
GitHub
Gitee

### 2.3.4 自动化构建工具

Gradle
Maven
SBT
ANT

### 2.3.5 虚拟化工具

VMware
VirtualBox
Vagrant
docker

### 2.3.6 CI & CD工具

Jenkins
Hudson
Travis CI
Circle CI
Gitlab CI

### 2.3.7 自动化测试工具

Appium
Selenium
Mock
Jmeter

### 2.3.8 自动化运维工具

Ansible
Puppet
SaltStack
Chef

### 2.3.9 监控管理工具

Zabbix
ELK Stack
Amazon CloudWatch
prometheus
  
PS：只是摘了一部分工具出来。

  

## 2.4 CI & CD 介绍

CI（Continuous integration，持续集成）：通俗讲就是研发人员写的代码可以持续的集成到整体代码中，并进行自动化测试。这样做可以快速发现错误，每完成一点更新就集成到主干，防止分支大幅偏离主干，大大提高了工作效率，让产品快速迭代的同时还能保持高质量。

CD（Continuous Delivery，持续交付）：频繁的将软件的新版本交给质量团队或者用户，以供评审，如果通过就进入生产阶段。持续交付可以看作持续集成的下一步。它强调的是：不管怎么更新，软件是随时随地可以交付的。

CD（Continuous Deployment，持续部署）：是持续交付的下一步，指的是代码通过评审以后，自动部署到生产环境。持续部署的前提是能自动化完成测试、构建、部署等步骤。注：持续部署和持续交付的区别就是最终部署到生产环境是自动化的。

  

## 2.5 CI & CD 流程
  一般中等规模的互联网公司都会有四套环境，开发（dev，此环境完全交于开发人员维护）、测试（test，此环境完全交于测试人员维护）、预发（pre）、生产（prd），完整流程应该是将代码先合并到 test 分支，如下：

提交代码合并到 test 分支。开发人员向 test 分支提交代码。推代码操作自动触发构建（build），就是将源码转换为可以运行的实际代码。
第一轮测试。测试人员拿 test 分支代码构建出的程序包运行测试，如果测试不通过，把结果返回给开发人员，开发继续修改代码提交到 test 分支，再自动打包，以此循环，直到测试通过进入下一步。
提交。开发人员将测试通过的 test 分支代码合并入 pre 分支，自动构建打包。
第二轮测试。测试人员拿 pre 分支代码构建出的程序包运行测试，如果测试不通过，把结果返回给开发人员，开发继续修改代码提交到 test 分支，再自动打包，以此循环。注意是直接打回到最底层的 test 分支，重新来过。
部署。pre 的包测试没问题后，后续 prd 环境就直接使用 pre 环境的包，生产环境的部署一般都是由运维人员操作。
  
PS：此流程不是一种标准，不代表所有公司的情况

