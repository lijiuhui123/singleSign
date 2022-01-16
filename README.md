## 1.单点登录系统的实现
  创建一个单点登陆系统
  ![传统登录](https://user-images.githubusercontent.com/48615126/149646008-e4837acc-afe1-43dc-960f-3cdf56d143ef.png)

单点登录流程图

  ![30093608_zJfw](https://user-images.githubusercontent.com/48615126/149646326-d29c4a20-1ceb-47f2-b024-71e85929bc4e.png)

  ![30093622_609p](https://user-images.githubusercontent.com/48615126/149646329-74ef6900-cac4-45a3-b98b-128b04ece4f3.png)
  
![2022-01-16_151637](https://user-images.githubusercontent.com/48615126/149649600-ce7336c3-0f81-4d98-8bf7-0f808a20d425.png)


  ### SSO 单点登录
   单点登录指的是在公司内部搭建一个公共的认证中心，公司下的所有产品的登录都可以在认证中心里完成，一个产品在认证中心登录后，再去访问另一个产品，可以不用再次登录，即可获取登录状态。
  #### 1. SSO 机制实现流程
  用户首次访问时，需要在认证中心登录：
 1.用户访问网站 a.com 下的 pageA 页面。
 2.由于没有登录，则会重定向到认证中心，并带上回调地址 www.sso.com?return_uri=a.com/pageA，以便登录后直接进入对应页面。
 3.用户在认证中心输入账号密码，提交登录。
 4.认证中心验证账号密码有效，然后重定向 a.com?ticket=123 带上授权码 ticket，并将认证中心 sso.com 的登录态写入 Cookie。
 5.在 a.com 服务器中，拿着 ticket 向认证中心确认，授权码 ticket 真实有效。
 6.验证成功后，服务器将登录信息写入 Cookie（此时客户端有 2 个 Cookie 分别存有 a.com 和 sso.com 的登录态）。
  
1. SSO 机制实现流程
  发布服务
  前台系统调用单点登录系统
  
## 2.session共享



