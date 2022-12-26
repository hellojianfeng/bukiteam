# bukiteam
develop social network for team
## 系统表述
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

![image](https://user-images.githubusercontent.com/3657139/209531785-3727e6f2-745e-430f-85fc-6d9c57f2df3d.png)


![image](https://user-images.githubusercontent.com/3657139/209528751-44c04c27-cbaf-4190-9e9c-2def0325afe2.png)





