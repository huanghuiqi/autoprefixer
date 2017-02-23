# autoprefixer
自动添加浏览器前缀处理器，本文示范如何在Webstorm中使用Autoprefixer
## 关于Autoprefixer
Autoprefixer是一个后处理程序，不象Sass以及Stylus之类的预处理器。它适用于普通的CSS，可以实现css3代码自动补全。也可以轻松跟Sass，LESS及Stylus集成，在CSS编译前或编译后运行。详情见，https://github.com/postcss/autoprefixer。  

当Autoprefixer添加前缀到你的CSS，还不会忘记修复语法差异。这种方式，CSS是基于最新W3C规范产生： 

示例：CSS代码
```
a {
     background : linear-gradient(to top, black, white);
     display : flex
}
```
编译后的CSS代码
```
a {
    background : -webkit-linear-gradient(bottom, black, white);
    background : linear-gradient(to top, black, white);
    display : -webkit-box;
    display : -webkit-flex;
    display : -moz-box;
    display : -ms-flexbox;
    display : flex
}
```
##在Webstorm上具体的安装和配置   

####第一步：安装 autoprefixer
```
     npm install autoprefixer -g
```
####第二步：安装 postcss-cli
```
     npm install postcss-cli =g
```
####第三步：配置External Tools
     打开Webstorm设置，Preferences -> Tools -> External Tools 点击新增按钮

####第四步：填写具体配置
     1、Name : autoprefixer   
     
     2、Program : 填入你的postcss-cli 的PATH 例：C:\Users\Administrator\AppData\Roaming\npm\postcss.cmd   
     
     3、Parameters :　-u autoprefixer -o $FileDir$\$FileName$ $FileDir$\$FileName$   
     
     4、Working directory : $ProjectFileDir$   
     
     
配置好后，你可以在css，或sass文件中右键，就可以在右键菜单中看到External Tools – autoprefixer，点击搞定~
