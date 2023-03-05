# bukiteam
develop notification app for team with elaborate role access control
## 系统简述
系统的实质是一个面向团队的通知系统（notification app）以及可以实现对通知信息的精准的权限控制。
### 核心功能包括：
1. 用户可以下载app并且注册为用户
2. 用户可以将通讯联系方式加入app（类似what app）
3. 用户可以自由创建team（类似what app group）
4. 在team中，可以创建notification（其中notification包含：信息部分，评论部分，附件部分和Actions部分，每个部分都可以进行精细的访问控制）。在team中，还可以创建不同类型的notification，notification的类型实际上就是一种对notification访问控制的组合，例如：一个公司人事部的notification，包含的访问控制：可以发送notification的角色是人事部成员，可以看的角色是所有member，可以评论的是管理成员等等。一些固定的notification可以定义为notification 类型，初次之外还可以临时发送自由定义的notification（发送的时候对访问进行自由定制）
5. 在创建team的时候，会默认创建member role， 创建者默认是member role admin， 每个角色都有至少一个admin， 可以由admin加入更多admin成员，admin成员是控制角色访问资源的核心角色
6. 每个成员都可以自由创建角色，但将成员加入角色时候，需要加入者的admit。
7. 当把某个角色加入资源访问时候，需要role的admin approve
8. 每个在team中的成员，可以看见两个主要列表，一个列表是notification，是和成员相关的notification，成员没有访问权限的notification不会显示。成员可以在具体的notification上执行相关操作，比如评论，访问附件，访问action中的链接等等。另外一个列表就是用户加入的角色群组，这个角色群发布一些和角色相关的信息，比如角色可以访问的资源，角色加入某个资源访问，退出某个资源访问，某某加入角色，某某退出角色等等。
9. 以后可以考虑将notification方便的发送到手机，邮件或者更多的客户端。

### 核心应用（不仅限于）
1. 团队可以得到认证并购买官方，从而变成一个机构或者公司的通知管理系统。
2. 可以非常灵活的定制团队（或者机构）的通知功能，特别是信息发送要求多而复杂的团队。
3. 在不用任何代码的情况下，就可以非常方便的实现审批系统。具有创建审批流程方便，创建审批流程功能强大，执行简单的特点，是最好的审批流程系统。
4. 在不需要任何代码的情况下，可以很方便的成为团队（机构）的信息发布系统（更高级的微信企业公众号），企业可以很方便定制企业的信息的发布内容（信息，附件等对企业发布来说完全足够了，随着软件系统成熟，会提高越来越强大的信息编辑功能），可以很方便定制信息发布的人群。
5.可以很方便的和其他系统对接，成为众多软件系统的访问入口，类似微信小程序和企业公众号的访问入口功能（功能更强大和更方便的企业公众号系统）。比如一个机构需要喝多应用app，客户关系管理系统，企业内部审批系统，供应链管理系统等等，那么用notification的方式就可以让团队成员进入机构的各种系统，后台系统可以专注数据管理，而notification部分则能解决信息通知和权限控制。

### 基本设计

#### 手机界面设计（初步框架）

##### 通知频道
![image](https://user-images.githubusercontent.com/3657139/222937927-b0d011a7-38aa-434b-9ee2-67519bcb0993.png)

##### 聊天频道
![image](https://user-images.githubusercontent.com/3657139/222937950-34eef175-adb8-4dab-995e-9b5510304a69.png)






