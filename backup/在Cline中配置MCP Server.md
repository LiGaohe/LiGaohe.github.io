# 安装Cline并添加MCP server
## vs code安装Cline
拓展中下载Cline
## 配置Cline
### 安装Node.js
使用Cline首先需要安装Node.js,前往官网下载：https://nodejs.org/en/

安装完成后，命令行输入`node -v`和`npm -v`检查是否安装成功；
### 配置环境变量
#### 1.找到安装的目录 D:\Program Files\nodejs，在安装目录下新建两个文件夹【node_global】和【node_cache】；
命令窗口输入以下命令

①npm config set prefix “你的路径\node_global” （复制你刚刚创建的“node_global”文件夹路径），例如：
```bash
npm config set prefix "D:\Program Files\nodejs\node_global"
```
②npm config set cache “你的路径\node_cache” （复制你刚刚创建的“node_cache”文件夹路径）

#### 2.配置环境变量：
①此电脑-右键-属性-高级系统设置-环境变量-系统变量-新建
变量名：NODE_PATH
变量值：你的路径\node_global\node_modules （复制你刚刚创建的“node_global”文件夹路径）
```md
Tips: 如果输入变量值之后没有自动创建【node_modules】文件夹，就在【node_global】下手动创建一个【node_modules】文件夹，再复制你创建的【node_modules】文件夹的路径地址到变量值
(复制不能省)
```
②编辑用户变量中的Path，将默认的 C 盘下【 AppData\Roaming\npm 】修改成 【node_global】的路径，点击确定
③在【系统变量】中选择【Path】点击【编辑】添加【%NODE_PATH%】，随后一直点击【确定】
#### 3.验证
输入命令：
```bash
npm config get prefix
npm config get cache
```
如果显示你刚刚设置的路径【D:\Program Files\nodejs\node_global】和【node_cache】，则表示配置成功
#### 4.配置镜像源
淘宝镜像
```bash
npm config set registry http://registry.npm.taobao.org
```
华为镜像
```bash
npm confg set registry https://mirrors.huaweicloud.com/repository/npm/
```
 查看是否成功：
```bash
npm config get registry
```
如果要恢复npm默认镜像，可以输入以下命令
```bash
npm config set registry https://registry.npmjs.org
```

### 获取OpenRouter API Key
前往OpenRouter官网：URL_ADDRESS前往OpenRouter官网：https://openrouter.ai/，
注册账号并登录，进入控制台，点击API Keys，点击Create New Key，创建一个新的API Key，复制API Key。
### 安装uv
前往github下载uv：https://github.com/astral-sh/uv/releases
下载二进制文件，解压，按照提示安装即可；输入命令`uv --version`检查是否安装成功，不成功可重启电脑。
### 安装MCP server
到`MCP Server`的`installed`界面，复制需要的MCP Server的“提示词”配置，例如：
```json
{
  "mcpServers": {
    "fetch": {
      "isActive": true,
      "command": "uvx",
      "args": [
        "mcp-server-fetch"
      ]
    }
  }
  
}
```
保存后尝试运行，可以运行。