# jenkins_declarative

## Branch upload_file:


## 1) Method with input:
we will create a file input :
```
script{
    def inputFile = input message: 'Upload file', parameters: [file(name: 'file.txt')]
    new hudson.FilePath(new File("$workspace/file.txt")).copyFrom(inputFile)
    inputFile.delete()
}
```
we can check if the file is download with :
```
steps{
    echo fileExists('file.txt').toString()
}
```

## 2) Error with Scripts not permitted:
Error example and solution:
<p align="center">
  <img width="800" height="500" src="https://github.com/YonathanGuez/jenkins_declarative/blob/upload_file/img/solution_error.png">
</p>
we use some library and jenkins need our autorisation for that : 
```
method hudson.FilePath copyFrom hudson.FilePath
method hudson.FilePath delete
new hudson.FilePath java.io.File
new java.io.File java.lang.String
```
we will put this into Jenkins > Management > ScriptApproval

## Why not use file Parameter :
File parameter not import files into declarative pipeline it s a bug 
