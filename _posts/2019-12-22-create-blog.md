## 如何搭建Git Page 博客

```
author:zhu
data:2019-12-12
time:23:13
```



#### 1.创建仓库：`username.github.io`

#### 2.下载jekyll 主题

+ 随便在`jekyll theme` 找一个喜欢的主题，`clone` 下来

#### 3.配置Ruby环境

+ 选择自己系统下载安装方式

  + `windows`安装可以使用工具` RubyInstaller `
  + 记得勾选将`ruby`加入系统环境变量路径中
  + 勾选`800M`那个拓展库,忘记叫啥了

+ 更换`gem`源

  + 国内源：` https://gems.ruby-china.com/ `

  + 先删除官方源，再安装国内源

  + 具体可能用到的命令：

    ```powershell
    gem sources -l   #查看所有的源
    gem sources --remove 想删的源  #删除指定源
    gem sources --add 添加的源  #添加源
    ```

    

#### 4.安装jekyll

```powershell
gem install jekyll
```

#### 5.安装bundler

```ruby
gem install bundler
```



#### 6.进入你下载的主题的文件夹，绑定主题

```ruby
bundle install
```

#### 7.启动jekyll服务器

```ruby
jekyll server
```

+ 成功后你可以访问`127.0.0.1:4000`看到你的主题效果

+ 你可以修改主题的`_config.yml`文件的信息为你的信息

+ 有前端基础的，可以改页面、样式等

  

  

#### 8.将修改好的主题推送到远端仓库

#### 9.文章都放在`_post`文件夹，

+ 需要安装固定的格式命名
+ 放入该文件夹后，再启服务器将文本转化为网页
+ 再次推送远程仓库

#### 10.常见错误：

+ 端口号被占用：

  ```shell
  $ jekyll server
  Configuration file: F:/BlogGit/_config.yml
              Source: F:/BlogGit
         Destination: F:/BlogGit/_site
   Incremental build: disabled. Enable with --incremental
        Generating...
                      done in 0.72 seconds.
    Please add the following to your Gemfile to avoid polling for changes:
      gem 'wdm', '>= 0.1.0' if Gem.win_platform?
   Auto-regeneration: enabled for 'F:/BlogGit'
                      ------------------------------------------------
        Jekyll 4.0.0   Please append `--trace` to the `serve` command
                       for any additional information or backtrace.
                      ------------------------------------------------
  
  ```

  解决方法：
  
  ```ruby
  port: 4005  #在配置文件后加一行
  ```
  
  

