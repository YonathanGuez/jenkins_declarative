# jenkins_declarative

## Branch parameter_jenkins:

### 1) Configuration Parameters :
We need to add all paramemeters in jenkinsfile to our parameter:

<p align="center">
  <img width="800" height="500" src="https://github.com/YonathanGuez/jenkins_declarative/blob/parameter_jenkins/img/config_add_parm.png">
</p>
<p align="center">
  <img width="800" height="500" src="https://github.com/YonathanGuez/jenkins_declarative/blob/parameter_jenkins/img/config_add_parm2.png">
</p>

### 2) Configuration Branch :
For this example we need to change the branch and work on parameter_jenkins:
<p align="center">
  <img width="800" height="500" src="https://github.com/YonathanGuez/jenkins_declarative/blob/parameter_jenkins/img/conf_branch.png">
</p>

### Result:
Run the build and change those parameter if you want: 
<p align="center">
  <img width="800" height="500" src="https://github.com/YonathanGuez/jenkins_declarative/blob/parameter_jenkins/img/resulta_param.png">
</p>
We can see on the log if our build is validate:
<p align="center">
  <img width="800" height="500" src="https://github.com/YonathanGuez/jenkins_declarative/blob/parameter_jenkins/img/result_build.png">
</p>

## Delete all workspace:
We need to put this at the end of stages ( not inside ):
```
 post {
        always {
            cleanWs()
        }
    }
```
Result in the log :
```
[Pipeline] { (Declarative: Post Actions)
[Pipeline] cleanWs
[WS-CLEANUP] Deleting project workspace...
[WS-CLEANUP] Deferred wipeout is used...
[WS-CLEANUP] done
```

It Use full for keep space and do only tests verifications