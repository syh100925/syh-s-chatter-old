## syh's chatter

### 配置环境
* syh's chatter聊天器使用了Python语言与Flask架构
* 您可以使用以下命令来配置Python环境（确保您已经安装了pip）

  `pip install flask`

### 安装
* 使用以下命令下载并进入目录：

  ```
  git clone https://github.com/syh100925/syh-s-chatter.git
  cd syh-s-chatter
  ```

### 启动前的设置
* 打开`server.py`，可以使用`nano server.py`，也可以`vim server.py`等等
  * 编辑以下字段：
    ```
      ip = '127.0.0.1:8080'                           <-- 两个单引号里修改为你的服务器地址

      usernames = ['admin', 'syh', 'Star']            <-- 以Python列表形式保存用户名
      passwords = ['666', 'ccc', 'eee']               <--                    和密码
      user_colors = ['grey', 'yellow', 'LightBlue']   <-- 不同用户的颜色
                                                          写为html的颜色表达形式：
                                                          可以为：grey、rgb(0, 0, 0)等
    ```

### 快速启动
* syh's chatter仅凭一行命令即可运行：
  #### 对于Windows&Linux：
  * 环境需求：Python3、Flask
  
    `python server.py`
    或
    `python3 server.py`
  
  #### 后台运行（仅Linux）：
  * 环境需求：Linux系统（带nohup命令）
  * 使用命令：
    * 启动：`./start.sh`
    * 停止：`./stop.sh`之后会返回一个[PID]，使用`kill [PID]`来结束
    * 重置：
      * 运行状态下：登录聊天室的admin账户，输入`clear`即可
      * 关闭状态下：`./reset.sh`

### 更多设置
* 在`templates`目录下，有`login.html`和`chat.html`
* 你可以通过修改两个文件里面的`style`标签来达到不同的效果


* 在`chat.html`文件中，有以下字段：
  ```
  <script>
      setInterval(update, 10 * 1000)
          function update(){
              window.location.replace("{{ jump_ip }}" + "&text=" + document.getElementById("text_editor").value)
          }
  </script>
  ```
  * 您可以通过修改里面的`10 * 1000`来决定网页刷新的速度（单位：`ms`）
  * 注意，本项目的刷新原理只是将整个网页刷新，虽然会保留文本输入框中的内容，但在输入法中正在输入的字符将不会被保留，请酌情选择刷新间隔时间长短



