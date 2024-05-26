<!-- markdownlint-disable MD041 -->
<p align="center">
  <a href="https://nonebot.dev/"><img src="https://nonebot.dev/logo.png" width="200" height="200" alt="nonebot"></a>
</p>

<div align="center">

# nonebot-plugin-template

_✨ NoneBot 每日任务插件 ✨_


<a href="./LICENSE">
    <img src="https://img.shields.io/github/license/owner/nonebot-plugin-template.svg" alt="license">
</a>
<a href="https://pypi.python.org/pypi/nonebot-plugin-template">
    <img src="https://img.shields.io/pypi/v/nonebot-plugin-template.svg" alt="pypi">
</a>
<img src="https://img.shields.io/badge/python-3.10+-blue.svg" alt="python">

</div>

这是一个 nonebot2 插件项目的模板库, 你可以直接使用本模板创建你的 nonebot2 插件项目的仓库

<details>
<summary>模板库使用方法</summary>

1. 点击仓库中的 "Use this template" 按钮, 输入仓库名与描述, 点击 "  Create repository from template" 创建仓库
2. 在创建好的新仓库中, 在 "Add file" 菜单中选择 "Create new file", 在新文件名处输入`LICENSE`, 此时在右侧会出现一个 "
   Choose a license template" 按钮, 点击此按钮选择开源协议模板, 然后在最下方提交新文件到主分支
3. 全局替换`owner`为仓库所有者ID; 全局替换`nonebot-plugin-template`为插件名; 全局替换`nonebot_plugin_template`为包名; 修改
   python 徽标中的版本为你插件的运行所需版本
4. 修改 README 中的插件名和插件描述, 并在下方填充相应的内容

</details>

<details>
<summary>配置发布工作流</summary>

模块库中自带了一个发布工作流, 你可以使用此工作流自动发布你的插件到 pypi

> [!IMPORTANT]
> 这个发布工作流需要 pyproject.toml 文件, 并且只支持 [PEP 621](https://peps.python.org/pep-0621/) 标准的 pyproject.toml
> 文件

1. 前往 https://pypi.org/manage/account/#api-tokens 并创建一个新的 API 令牌。创建成功后不要关闭页面，不然你将无法再次查看此令牌。
2. 在单独的浏览器选项卡或窗口中，打开 [Actions secrets and variables](./settings/secrets/actions) 页面。你也可以在
   Settings - Secrets and variables - Actions 中找到此页面。
3. 点击 New repository secret 按钮，创建一个名为 `PYPI_API_TOKEN` 的新令牌，并从第一步复制粘贴令牌。

</details>

<details>
<summary>触发发布工作流</summary>
从本地推送任意 tag 即可触发。

创建 tag:

    git tag <tag_name>

推送本地所有 tag:

    git push origin --tags

</details>

## 📖 介绍

这里是插件的详细介绍部分

## 💿 安装

<summary>使用 nb-cli 安装</summary>

    nb plugin install nonebot-plugin-daily-task

<summary>pip</summary>

    pip install nonebot-plugin-daily-task

打开 nonebot2 项目根目录下的 `pyproject.toml` 文件, 在 `[tool.nonebot]` 部分追加写入

    plugins = ["nonebot_plugin_daily_task"]

## ⚙️ 配置

在 插件 的`config.py`文件中修改下表中的配置

|           配置项            |  类型  |  默认值  |     说明     |
|:------------------------:|:----:|:-----:|:----------:|
|    daily_task_bot_id     | str  |   无   |   Bot QQ   |
|    daily_task_db_name    | str  | daily |   数据库名称    |
|  daily_task_start_hour   | int  |  10   | 每日任务提醒开始时间 |
|   daily_task_end_hour    | int  |  23   | 每日任务提醒结束时间 |
| daily_task_interval_hour | int  |   2   | 每日任务提醒间隔时间 |
|   daily_task_priority    | int  |  10   | 每日任务提醒优先级  |
|    daily_task_enabled    | bool | False | 是否启用每日任务提醒 |

## 🎉 使用

### 指令表

|       指令       |    功能    |    权限     |
|:--------------:|:--------:|:---------:|
|     daily      |   插件简介   |    所有人    |
|  daily.help/h  | 查看插件帮助信息 |    所有人    |
|  daily.add/a   |  添加每日任务  |    所有人    |
|  daily.del/d   |  删除每日任务  |    所有人    |
| daily.modify/m |  修改每日任务  |    所有人    |
| daily.query/q  |  查询每日任务  |    所有人    |
| daily.finish/f |  完成每日任务  |    所有人    |
| daily.start/s  |  启用每日任务  | SUPERUSER |
| daily.stop/st  |  停用每日任务  | SUPERUSER |

### 效果图

