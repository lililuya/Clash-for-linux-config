# Clash-for-linux-config
## 1.linux下的clash安装包（linux带图形界面的clash配置）
+ (Clash-for-linux)[https://drive.google.com/file/d/1PS5MEw35xFqM9-lRAfHQ5hs_B5Ex2v_T/view?usp=sharing]
### 1.1使用方法
```bash
# 下载后解压
tar -xzvf Clash-*...

# 授权限
mv Clash-*... Clash
cd Clash
sudo chmod +x cfw

# 开启clash-GUI
./cfw
```
### 1.2 配置
+ 填入订阅链接(链接或者config.yaml)
+ 订阅链接参考[plane](翻墙机场.com)
+ 设置代理端口
  + `Ubuntu-->Setting-->NetWork-->Proxy-->Mannual`
  ```json
  http:127.0.0.1:7890
  https:127.0.0.1:7890
  ``` 
## 2. linux下纯shell配置clash
 (clash-linux-amd64.tar.gz)[https://github.com/Kuingsmile/clash-core/releases/tag/1.18]
 ### 2.1 使用方法
```bash
unzip clash*
chmod +x clash
# clash默认读取当前目录下的config.yaml文件，或者手动指定
.clash -d .
# 执行后，会同时开启HTTP代理和Sockets代理
```

### 2.2 zai 在终端中使用
```bash
# 可以选择配置在.bashrc里面，全局shell生效
export https_proxy=http://127.0.0.1:7890 
export http_proxy=http://127.0.0.1:7890
export all_proxy=socks5://127.0.0.1:7890
# 7890是你的代理端口，在config.yaml里面配置
# config.yaml这个文件来自于你的订阅链接
```
+ 查看clash Dashboard
  + 具体访问：http://127.0.0.1:9090(http://serverip:9090)
   
### 2.3 结合gdown下载大文件
#### 2.3.1 正常下载一些小文件和文件夹
- Google的文件或者文件夹的share格式
  `https://drive.google.com/file/d/FILE_ID/view?usp=sharing
https://drive.google.com/file/d/xxxxxxxxxxxxxxxxxx/view?usp=sharing
- 下载方式
```bash
gdown 'https://drive.google.com/uc?id=FILE_ID'
```
#### 2.3.2 下载异常情况
- Too many users have viewed or downloaded this file recently. Please
try accessing the file again later. If the file you are trying to
access is particularly large or is shared with many people, it may
take up to 24 hours to be able to view or download the file. If you
still can't access a file after 24 hours, contact your domain
administrator.  
  - 一般是下载文件过大，或者访问过多导致的问题
  - 此时需要google api
- 获取google api
  - 进入链接 https://developers.google.com/oauthplayground/
  - 在 Select the Scope 栏复制 https://www.googleapis.com/auth/drive.readonly
  - 点击Authorize APIs 然后 Exchange authorization code for tokens
  - 复制 Access token
  - 在命令行终端运行
```bash
	curl -H "Authorization: Bearer Access token" https://www.googleapis.com/drive/v3/files/FILE_ID?alt=media -o FILE_NAME
```


### 3. 参考
- [gdwon下载大文件](https://blog.csdn.net/weixin_45607635/article/details/122042220)
- [clash安装教程](https://clever99.com/linux-using-clash)
