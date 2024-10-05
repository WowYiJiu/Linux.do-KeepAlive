- 本脚本适用于浏览[LINUX DO](https://linux.do/)帖子和点赞，支持多账号
### 使用教程
>测试环境 Python 3.10、selenium 4.23.1

**1. 青龙面板配置镜像加速 (系统设置->依赖设置)**
- Python 软件包镜像源 `http://mirrors.aliyun.com/pypi/simple/`
- Linux 软件包镜像源 `https://mirrors.aliyun.com`
  
**2. 青龙面板依赖 (依赖管理->创建依赖)**
- 选择 **Python3** 类型, 输入名称: `selenium`
- 选择 **Linux** 类型, 分别创建 `chromium` 和 `chromium-chromedriver`

**3. 引入脚本 (脚本管理->右上角创建)**
- 根目录新建 `Linux.do.py`和`notify.py` 两个文件
- 拷贝两个文件对应内容
  
**4. 配置定时任务 (定时任务->创建任务)**
- 任务名：Linux.do浏览帖子
- 命令：task Linux.do.py
- 定时：0 7 * * *
>定时规则请自行修改

>不容易啊，全靠始皇的Shared
### 环境变量（多账号换行）
```
export LINUXDO_USERNAME = "neo@Linux.do
neo2@Linux.do"
export LINUXDO_PASSWORD = "IamNeo!
IamNeo!"
export SCROLL_DURATION = 5 // 首页滚轮滚动时间，控制加载帖子数量，默认为0秒
export VIEW_COUNT = 1000 // 点赞要求的帖子浏览量，默认大于1000浏览量才进行点赞
```
- 示例图
![首次运行示例](https://im.wowyijiu.com/file/7571e84634def1d0a0cea.png)
![运行日志](https://im.wowyijiu.com/file/11b45f26c2ae6f3569536.png)
![消息推送](https://im.wowyijiu.com/file/cbe6978cc811c0db98079.png)
