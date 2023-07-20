# 服务器配置

## git dns

windows的host在C:\Windows\System32\drivers\etc\host  
linux的host在/etc/hosts

把下面这段复制到host里(windows可以考虑用vscode修改)

```bash
140.82.114.3  github.com
108.160.167.165 github.global.ssl.fastly.net
185.199.110.153 assets-cdn.github.com
```

linux下可以选择  

```bash
sudo sh -c 'sed -i "/# GitHub520 Host Start/Q" /etc/hosts && curl https://raw.hellogithub.com/hosts >> /etc/hosts'
```

接着刷新dns  
windows  

```cmd
ipconfig /flushdns
```

linux  

```bash
sudo apt install nscd
sudo systemctl restart nscd
```

## 无法访问微软商店

可以先试试把代理工具关了

如果不行
win+r, 输入inetcpl.cpl
勾上TLS 1.1,TSL1.2

![internet attribute](img/internet.png)

## 字体

下载下面这4个  
[MesloLGS NF Regular.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)  
 [MesloLGS NF Bold.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)  
  [MesloLGS NF Italic.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)  
[MesloLGS NF Bold Italic.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)  

win可以直接安装  
linux  

```bash
sudo apt-get install ttf-mscorefonts-installer fontconfig -y
```

```bash
sudo mkdir -p /usr/share/fonts/MesloLGS
sudo cp *.ttf /usr/share/fonts/MesloLGS
sudo chmod -R 777 /usr/share/fonts/MesloLGS

sudo fc-cache -fv
```

## terminal

在微软商店

![win_terminal](img/win_terminal.png)

### 添加conda

打开windows terminal  
设置里  
![在这里插入图片描述](img/conda1.png)  
添加新配置文件->新建空配置文件  
![在这里插入图片描述](img/conda2.png)
名称：Anaconda
命令行

```cmd
%windir%\System32\cmd.exe "/K" D:\Miniconda3\Scripts\activate.bat D:\Miniconda3
```

可以从这里抄
![在这里插入图片描述](img/conda3.png)  
![在这里插入图片描述](img/conda4.png)  
图标  

```bash
D:\Miniconda3\Lib\site-packages\conda\shell\conda_icon.ico
```

保存
![在这里插入图片描述](img/conda5.png)

![在这里插入图片描述](img/conda6.png)

### 添加git

打开安装包（不用卸载之前的） 
其他的默认就行  
![在这里插入图片描述](img/git1.png)  
重新打开windows terminal  
![在这里插入图片描述](img/git2.png)  
如果没有也可以手动配置  
![在这里插入图片描述](img/git3.png)  
