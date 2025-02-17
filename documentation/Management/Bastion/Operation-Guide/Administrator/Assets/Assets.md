# 主机管理


主机管理用于添加、导入、编辑主机功能。

**新建主机**

通过【资产】-【主机管理】创建主机，创建方式包括：手动创建、导入京东云主机、从本地文件导入。

![](/image/Bastion/hostList.png) 

- 手动创建：单击添加主机进入创建页，按页面要求填写主机信息，完成后单击创建主机。
- 导入京东云主机：单击导入京东云主机，在弹窗中选择需要导入的云主机。
- 从本地文件导入：单击从本地文件导入，可以批量导入资源。


**手动添加主机**

1、 进入资产 > 主机管理页，单击“添加主机”进入创建页。

2、 在新建主机页面，按规范填写主机名、IP地址、资源类型，端口协议，选择账户（也可重新创建），单击“确定”按钮完成主机创建。

   ![](/image/Bastion/addHost.png) 
   

**导入京东云主机**

2、 进入【资产】-【主机管理】，选择导入京东云主机。

 ![](/image/Bastion/import-ecs1.png) 
    
  1） 在导入京东云主机页面，勾选要导入堡垒机的云主机实例，并单击确定。
  
  ![](/image/Bastion/import-ecs2.png) 
  
  2） 导入成功之后，单击主机列表中的 编辑 按钮，进行添加主机账号。

**从本地文件导入**
 
3、进入【资产】-【主机管理】，选择“从本地文件导入”。

![](/image/Bastion/hostimport.png) 

  1） 在“从本地文件导入”弹窗中，点击 模版下载。
  
  ![](/image/Bastion/templatedownload.png)
  
  2） 填写模板，导入需要提供的信息如下
    
  ![](/image/Bastion/modelHost.png) 
  
  3） 完成模版之后，点击 上传文件。
  
**测试连通性**  
  
1、 导入成功之后，在列表中检查连通性是否正常

2、 鼠标悬浮连通性状态，可以详情 或 重新测试连通性

 ![](/image/Bastion/test.png) 

3、 点击列表中的登录 ，可以尝试登录主机

 ![](/image/Bastion/onBoard.png) 
 
 
**编辑主机**

操作步骤

1、 进入【资产】-【主机管理】。

2、 在主机列表中，单击 编辑，支持添加主机账号、修改协议及端口等。

  ![](/image/Bastion/editHost.png) 
  

**停用主机**

主机被停用之后将不能通过堡垒机登录，直到管理员重新设置为启用。

操作步骤

1、 进入【资产】-【主机管理】

2、 在主机列表中选择需要停用的主机，点击“更多”-“停用”操作；

  ![](/image/Bastion/stopHost.png) 

**启用主机**

操作步骤

1、 进入【资产】-【主机管理】。

2、 在主机列表中选择已停用的主机，点击“更多”-“启用”操作。即可通过堡垒机登录主机。

  ![](/image/Bastion/startHost.png) 

**删除主机**

操作步骤

1、 进入【资产】-【主机管理】。

2、 在主机列表中选择已停用的主机，点击“更多”-“删除”操作，完成操作。



