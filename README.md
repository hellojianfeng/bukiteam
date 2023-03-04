# bukiteam
develop notification app for team with elaborate role access control
## 系统简述
系统的实质是一个面向团队的通知系统（notification app）
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
5.可以很方便的和其他系统对接，成为众多软件系统的访问入口，类似微信小程序和企业公众号的访问入口功能。比如一个机构需要喝多应用app，客户关系管理系统，企业内部审批系统，供应链管理系统等等，那么用notification的方式就可以让团队成员进入机构的各种系统，后台系统可以专注数据管理，而notification部分则能解决信息通知和权限控制。


系统包含的主要功能：
### 注册和登录
每个用户都可以在系统里面注册并登录系统。用户可以绑定手机和电邮，并且用电邮或者手机收验证码<br />
类似whatapp,可以引入手机的contract
### 创建团队
每个人都可以创建团队(team)，默认情况下，创建者会加入admin角色，admin的成员以后还可以添加，每个team至少有一个admin成员。
#### admin包含的功能可能包括（以后可以根据情况增加或者减少）
<ol>
  <li>操作team的设置，包括子team的设置</li>
  <li>操作team的role以及包括添加role的成员</li>
  <li>操作team的operation</li>
</ol>

#### 团队创建的基本流程
![image](https://user-images.githubusercontent.com/3657139/214242946-c26bf1aa-9056-487d-a707-fed986c9347f.png)


### 添加团队角色并且添加角色人员
<ol>
  <li>每个团队的角色role具有唯一的id</li>
  <li>除了admin有操作角色的权限，也可以添加role以及对应的operation对角色进行处理</li>
</ol>

### 添加角色操作
<ol>
  <li>一般来说，每个角色可以添加一个或者多个操作operation</li>
  <li>除了admin有操作操作的权限，也可以添加role以及对应的operation对operation进行处理</li>
</ol>

操作operation是功能的核心功能，系统管理员或者操作管理员可以根据团队功能的需要方便的添加operation，operation添加之后，拥有角色的人员就可以对operation进行使用，一般来说，一个operation有几种使用方式：
<ol>
  <li>对operation的查看view，这种模式下，用户可以收到operation的notification并查看operation的情况，但不能进行操作</li>
  <li>对operation的执行execute，这种模式下，可以收到notification并执行相应的操作</li>
</ol>


### 添加子团队
一个团队可以有很多子团队，子团队可以加入tag或者用categroy组织起来，可以很方便的进入关联团队，子团队的一些分类有：
<ol>
  <li>母公司团队可以是子团队的一种</li>
  <li>子公司可以是子团队中的一种</li>
  <li>供应链机构可能是子团队中的一种</li>
  <li>各种关联团队或者机构可能是子团队中的一种</li>
</ol>

### 信息中心 message center 和 message channel
每个team 会定义一个 message center，message center 可以创建 message channnel. message channel是某些人，某些角色+某类信息的组合，默认的channel 包括：team-all,这个显示team内所有信息，all-operation，显示所有operation的信息，all-message(no operation).除了默认的channel,team 管理员可以建一些 role+message 类型的组合形成的channel.在channel内，对应人员看和操作信息。

手机端和电脑端的app的一些界面设计：

Message Center:
![image](https://user-images.githubusercontent.com/3657139/214238271-1fd762df-69c6-4968-b61f-ac9fb0e865d7.png)

Add Message Channel:
![image](https://user-images.githubusercontent.com/3657139/209528751-44c04c27-cbaf-4190-9e9c-2def0325afe2.png)

Add Operation:
![image](https://user-images.githubusercontent.com/3657139/209610931-53fbfbcb-140a-4aaf-a2f6-3417d98b6701.png)

Operations in tablet or pc
![image](https://user-images.githubusercontent.com/3657139/210072519-52c80c72-9b20-4878-87c5-4c52efb186df.png)

Messages in tablet or pc
![image](https://user-images.githubusercontent.com/3657139/210126844-a19dbfc5-2895-4847-92ea-a8401597c2e7.png)



### 案例

## 餐馆订购厨房万能烤箱的案例
整个过程大致包含一下步骤：
<ol>
  <li>餐馆负责订购人员，厨师长，审批人员，财务人员以及设备商的销售人员，财务人员和审批人员首先建一个team</li>
  <li>销售人员首先建一个channel，包含销售人员，和厨房采购和厨师长等</li>
  <li>销售人员首先发送一个message，通知采购人员和厨师长，列出可以提供的万能烤箱类型和价格等，产品信息可以用附件方式发出，或者添加一个链接</li>
  <li>采购人员可以建立另外一个channel，包含厨房的相关人员，并发送一个信息，将销售人员的产品信息在内部message中进行讨论，采购人员可以根据权限将销售人员的产品列表添加到内部信息里面进行讨论，同时可以在信息中控制访问权限，某些人员可以了解信息，但不能参与讨论等等</li>
  <li>当达成购买意向之后，可以由销售人员发出报价单，报价单可以通过餐馆方的审批人员以及财务等进行审核，完成后签字返回销售人员，中间也可以包含购买方支付定金，并且让支付信息让相关人员知晓</li>
  <li>销售方也可以建立自己的channel，然后将发货方加入team，然后发出发货message，这个message可以通知购买方进行相应收货处理，还可以加入设备安装维护人员，并发出设备维护的message,安排好安装维护等事情</li>
  <li>购买完成之后，还可以通过message安排定期维护等工作</li>
</ol>

#### 说明：用channel和message以及message对附件，评论等控制，可以灵活完成业务流程，但等到业务流程相对固定之后，可以建立operation来执行，可以更加高效和一致，以上操作如果用operation方式执行，可能包含以下步骤：

<ol>
  <li>建立team并加入相关人员</li>
  <li>销售方建立一个报价的operation，然后销售人员启动报价的操作。报价操作启动之后，首先会发送一个产品列表的信息给采购方相关人员，由采购通过评论可以确定需要产品，最后销售方通过附件等方式将最后报价单发送给采购方</li>
  <li>采购方可以建立一个采购operation,然后由采购方发出采购信息，可以包括确认的采购合同，包括支付信息等附件，并通知销售方相关人员，通过评论以及附件等方式，销售方会确定收到采购方信息并通知发货等信息</li>
  <li>销售方建立一个发货的operation，并发送组织发货的信息，这个操作可以加入发货人员，可能是第三方的货运人员，这个信息会发送给相应人员，通过评论，message以及附件形式，可以确保相关的文档可以在销售方，发货方以及接收方之间进行交互，并能够完成发货的操作</li>
  <li>销售方可以建立设备维护operation，将维护人员加入，并确认好维护合同和操作细节</li>
</ol>

![image](https://user-images.githubusercontent.com/3657139/209620706-e26008ee-678b-40b6-825f-689bc5da13e7.png)

#### 案例研究：资产管理系统

##### 传统资产管理系统的实现

![image](https://user-images.githubusercontent.com/3657139/214466502-7585a142-88f5-4255-9236-b414ea2a0f24.png)

##### Bukiteam 架构实现资产管理系统

![image](https://user-images.githubusercontent.com/3657139/214793058-2170665f-8a8a-4bbd-a36a-013318493d27.png)

##### Basic db tables

![image](https://user-images.githubusercontent.com/3657139/217547904-b3ceb0ff-5431-41e7-abea-0596ab218c75.png)

![image](https://user-images.githubusercontent.com/3657139/217543688-e7e3b68b-96ed-498e-8117-de3217cccd0f.png)






