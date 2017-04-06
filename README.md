# ArtifactoryUploadScript
Script for Artifactory upload without Android SDK

- 配置
  - 配置Artifactory服务器信息
    - 在`~/.gradle/gradle.property`中追加如下配置:
    ```
    artifactory_user=账户名
    artifactory_password=密码
    artifactory_contextUrl=服务器地址
    ```
  - 在`artifact`目录下面放置`aar`文件
  - 并在`artifact`配置`package.json`, 格式如下
  ```
  {
  	"groupId": "YourGroupId",
  	"artifactId": "YourArtifactId",
  	"version": "YourPackageVersion",
  	"dependencies": [
        {
        	"groupId": "GroupIdOfDependency",
        	"artifactId": "ArtifactIdOfDependency",
        	"version": "PackageVersionOfDependency"
        },
        ...
  	]
  }
  ```
- 上传artifact
  - 执行`./upload.sh`
