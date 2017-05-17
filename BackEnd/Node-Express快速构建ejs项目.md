# Node.js基于Express框架搭建一个采用ejs模板的项目  
本文是笔者创建ejs模板项目的笔记，创建项目的机会比较少，大多数时间都是在自己建好的项目上增添细节，再次创建项目难免有些磕磕绊绊，记录下过程以方便以后查找。
另外，构建的是符合笔者习惯的风格的项目，所以此处页面文件采用后缀名.html而不是.ejs，因为没有是用jade模板，当然也就没有.jade啦~
 
### 首先注明一下版本  
<img width="25%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/1.png">  

### 项目初始化  
笔者的node和express都是全局安装的，在这里直接以桌面为演示路径  
执行命令 express -e test   
<img width="35%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/2.png">   
这时候已经建立了基本的骨架，但是依赖的文件还没有下载，进入文件夹内，执行 npm install
<img width="35%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/3.png">   
安装完毕后项目的初始化完成，运行 npm start，启动node服务器，检查有没有下载错误等异常（如果有就报错啦~，看控制台信息排查）  
<img width="45%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/4.png">   
打开浏览器，输入http://localhost:3000/  
<img width="45%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/5.png">  
正常运行，没问题。 
### 改造
  接下来我们看一下目录结构——  

<img width="15%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/6.png">   

在views文件夹中可以看到views的文件都是采用.ejs后缀的，但笔者习惯采用.html后缀的静态文件，所以就在这个的基础上进行改造。  
进入app.js文件中，在相应的位置把代码修改成下面这样。    
<img width="45%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/7.png">   
  
最后一步，将views文件夹里面的模板文件后缀改成.html，完工！  
<img width="15%" src="https://github.com/SteinsGateLab/Articles/blob/master/issue/BackEnd/Node-Express%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BAejs%E9%A1%B9%E7%9B%AE/8.png"> 

##### 这种构建项目形式可以让前端人员直接按照原来的方式写页面模板，不需要html2jade。个人开发项目，主要还是看个人喜好，目前更偏好直接写html而不是jade。
