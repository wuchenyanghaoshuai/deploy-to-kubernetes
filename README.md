```
本章节,详细介绍如何使用jenkins发版一个前端项目到kubernetes
```
# 准备工作部署一个gitlab并创建好group
```
1.1 centos安装gitlab省略
1.2 gitlab创建group并上传代码
1.3 创建三个group,分别为devops和kkb-release和code
1.4 devops 组内创建的项目分别为delivery kkb-front-flow-plugin kkb-k8s-mos-deploy-plugin
    1.4.1 delivery 组内的代码为
1.5 kkb-release 组内创建的项目为 release-template
1.6 code 项目创建的项目为 java-demo tupian 
```

```
1.部署一个jenkins
1.2 创建两个凭据,一个是jenkins用来拉代码的,一个是jenkins push docker image的
```
![image](https://user-images.githubusercontent.com/39818267/152107601-0a2b6c9f-93bc-48ac-8dd3-0fed732bb304.png)

```
2.1将前端pipeline代码
```
