# cicdtest
3个文件：
jenkinsfile: jenkins;
dockerfile: 做docker iamge;
index.html: 模拟复制到docker image的成果物，可以war包等;

镜像仓库使用的是Harbor.

上面的实验在2017就完成了。这次的作业想在AWS的环境中完成，但碰到一些问题，下面是思路：


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
        
   通过AWS CloudFormation 文件可以快速的部署整个CodePipeline
   
   

