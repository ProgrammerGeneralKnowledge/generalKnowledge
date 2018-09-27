# python小技巧  
## Python项目生成requirements.txt
* pigar 
[pigar](https://github.com/damnever/pigar)是一个 requirements tool，安装好之后， 进入到指定项目中执行命令 pigar即可，执行的时候会出现如下    
Try to search PyPI for the missing modules and filter some unnecessary modules? (y/[N])，   
选择N即可，如果输入y可能会检测很久，没必要     
pigar是生成指定目录下的依赖类库

* pip freeze   

    pip freeze > requirements.txt   
    
  pip freeze命令输出的格式和requirements.txt文件内容格式完全一样，因此我们可以将pip freeze的内容输出到文件requirements.txt中。在其他机器上可以根据导出的requirements.txt进行包安装。    
  pip freeze输出的是本地环境中所有三方包信息，但是会比pip list少几个包，因为pip，wheel，setuptools等包，是自带的而无法(un)install的，如果要显示所有包可以加上参数-all，即pip freeze -all  

* pipreqs  
安装  pip install pipreqs  ， 生成  pipreqs requirements.txt  ， pipreqs生成指定目录下的依赖类库

  
>  区别

  使用pip freeze保存的是当前Python环境下所有的类库，如果你没有用virtualenv来对Python环境做虚拟化的话，类库就会很杂很多，在对项目进行迁移的时候我们只需关注项目中使用的类库，没有必要导出所有安装过的类库，因此我们一般迁移项目使用pigar或者pipreqs，而pip freeze更加适合迁移整个python环境下安装过的类库时使用。
  
    

