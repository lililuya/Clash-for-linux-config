# Clash-for-linux-config
## 1.linux下的clash安装包
+ 注意，此方法需要linux具有图像化的界面才可以正常使用
+ (Clash-for-linux)[https://drive.google.com/file/d/1PS5MEw35xFqM9-lRAfHQ5hs_B5Ex2v_T/view?usp=sharing]
## 2.使用方法
+ 解压
```bash
tar -xzvf Clash-*...
```
+ 授权限
```bash
mv Clash-*... Clash
cd Clash
sudo chmod +x cfw
./cfw
```
+ 此时将有一个可视化的界面
  + 填入订阅链接
  + 订阅链接参考(plane)[翻墙机场.com]
+ 设置代理端口
  + Ubuntu-->Setting-->NetWork-->Proxy-->Mannual
```json
http:127.0.0.1:7890
https:127.0.0.1:7890
``` 
