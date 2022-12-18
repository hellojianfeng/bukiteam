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

### 添加子团队
一个团队可以有很多子团队，子团队可以加入tag或者用categroy组织起来，可以很方便的进入关联团队，子团队的一些分类有：
<ol>
  <li>母公司团队可以是子团队的一种</li>
  <li>子公司可以是子团队中的一种</li>
  <li>供应链机构可能是子团队中的一种</li>
  <li>各种关联团队或者机构可能是子团队中的一种</li>
</ol>
