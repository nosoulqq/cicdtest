
简单的Demo环境：
3个文件：
jenkinsfile: jenkins;
dockerfile: 做docker iamge;
index.html: 模拟复制到docker image的成果物，可以是war包等，根据应用服务器或者WEB服务以及想要发布的程序有关。
镜像仓库使用的是Harbor.

3个文件均放在github中，任意文件的变更触发Jenknis的Pipeline.

这次的作业在AWS的环境中完成，具体如下：

CodePipeline 支持的工具链：
    Source Code Repositories
        Amazon S3 (Versioned)
        AWS CodeCommit
        GitHub
    Build Providers
        AWS CodeBuild
        Jenkins
        Solano CI
    Deployment Tools
        AWS Elastic Beanstalk
        AWS CodeDeploy
        AWS CloudFormation
        
   通过AWS CloudFormation 可以快速的部署整个CodePipeline，实现Pipeline as code:
   模板文件：
   aws-codedeploy-codepipeline-starter-kit.template
   
   整个CodePipeline分4个阶段：
     Source Code: 导入代码，代码的提交或者修改触发整个CodePipeline流程
     Build: 在Jenkins里面构建app；
     Beta: CodeDeploy部署app在beta服务器；
     Prod: CodeDeploy部署app在prod服务器。
     
     通过CodeDeploy可以方便的把工件（app）部署到AWS的机器上，支持蓝绿部署。
     
     监控：cloudWatch, 与Auto Scaling groups结合使用，设置阀值来扩容或者缩容；
     
     
     
   
   

