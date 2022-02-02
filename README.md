```
本章节,详细介绍如何使用jenkins发版一个前端项目到kubernetes
```
# 准备工作部署一个gitlab并创建好group
```
1.1 centos安装gitlab省略
1.2 gitlab创建group并上传代码
1.3 创建三个group,分别为devops和kkb-release和code
1.4 devops 组内创建的项目分别为delivery kkb-front-flow-plugin kkb-k8s-mos-deploy-plugin(见图一)
    1.4.1 delivery 项目内的代码为 git@github.com:wuchenyanghaoshuai/delivery.git
    1.4.2 kkb-front-flow-plugin 项目内的代码为 git@github.com:wuchenyanghaoshuai/kkb-front-flow-plugin.git
    1.4.3 kkb-k8s-mos-deploy-plugin 项目内的代码为 git@github.com:wuchenyanghaoshuai/kkb-k8s-mos-deploy-plugin.git
1.5 kkb-release 组内创建的项目为 release-template(见图二)
    1.5.1 release-template 项目内的代码为 git@github.com:wuchenyanghaoshuai/release-template.git
1.6 code 组创建的项目为 java-demo tupian (见图三)
    1.6.1 java-demo 项目代码为 git@github.com:wuchenyanghaoshuai/java-demo.git
    1.6.2 tupian 项目的代码为git@github.com:wuchenyanghaoshuai/tupian.git
```
![image](https://user-images.githubusercontent.com/39818267/152109590-06e52a14-3eca-491a-a98d-5cddc3ef874d.png)
![image](https://user-images.githubusercontent.com/39818267/152109958-9b8c942e-f61a-4009-ba7d-2e0e9979c89b.png)
![image](https://user-images.githubusercontent.com/39818267/152110962-a3bd6f01-09ce-4141-92fe-1aac497d722a.png)

```
2.部署一个jenkins
2.1 创建两个凭据,一个是jenkins用来拉代码的,一个是jenkins push docker image的
```
![image](https://user-images.githubusercontent.com/39818267/152107601-0a2b6c9f-93bc-48ac-8dd3-0fed732bb304.png)

```
3.将前端和后端pipeline加入到jenkins中
    3.1 jenkins里面下载插件pipeline
    3.1 点击系统管理下的系统配置,在Global Pipeline Libraries字段下添加pipeline地址(见图四),三个devops内的项目都要加进去

```
![image](https://user-images.githubusercontent.com/39818267/152111919-811e6f62-09ef-40af-8c47-ac71d299cad7.png)
![image](https://user-images.githubusercontent.com/39818267/152111956-fd8e68ac-cd89-4aad-af5d-891f65d45a70.png)
![image](https://user-images.githubusercontent.com/39818267/152111979-0ca33b5c-7303-4f64-b2e1-045cccf43ee6.png)
![image](https://user-images.githubusercontent.com/39818267/152111993-53ed8619-7a13-48e2-9fc4-2803c5ce5d1b.png)
![image](https://user-images.githubusercontent.com/39818267/152112029-ae75e545-945f-425b-809a-c69828862ffd.png)
![image](https://user-images.githubusercontent.com/39818267/152112043-8773e954-66d7-4f28-8e2b-865a58301f67.png)

4.创建流水线并发版
    4.1 创建一个项目选择流水线
    4.2 参数化构建过程
    ![image](https://user-images.githubusercontent.com/39818267/152114277-87dd779f-229a-42fb-a67c-3fb7ca8342f3.png)
    ![image](https://user-images.githubusercontent.com/39818267/152114292-2b6b6194-ee6b-443f-bcea-a3f28ca1f949.png)
    4.3 点击构建即可
    ![image](https://user-images.githubusercontent.com/39818267/152113759-a4db674d-f900-438b-9c31-48415ef7d3d9.png)
    4.4 发布,选择分支和部署的环境
    ![image](https://user-images.githubusercontent.com/39818267/152114432-a0471fc7-dd1f-4351-ae7d-0011eae9c0ce.png)


