title: 代码审查工具Phabricator介绍
speaker: Hans Zhang
url: http://review.osvlabs.com
transition: move
files: /js/demo.js,/css/demo.css

[slide]
# 代码审查工具Phabricator介绍
<small>演讲者：Hans Zhang</small>

[slide]
## 界面展示
----
* 菜单 {:&.moveIn}
* 查询器
* 守护进程
    * 拉代码
    * 发邮件
    * 更新索引
* 帮助
* 注册

[slide]
## 核心功能Code Review使用
----
* 推送后审查：Audit {:&.bounceIn}
* 推送前审查：Differential

[slide data-transition=kontext]
## Audit设置
----
* 自动创建
    * 创建Herald规则 {:&.moveIn}
    * 针对Commits的Global规则
    * 指定条件
        * 仓库
        * Differential里面没有
    * 指定动作
        * 创建Audit
* Commit message中手工指定审查者：
    > Auditors: username1, username2

[slide]    
## Audit界面
----
* 默认查询器
    * 打开 Audit Required
    * 表示担忧 Concern Raised
    * 审核通过 Audited
* 审核操作
    * 开发者提交代码 {:&.moveIn}
    * 系统检查到Commits，发送邮件到审核者
    * 审核者打开审核页面
    * 检查代码，添加行评论
    * 确定操作（审核是否通过），添加评论
    * 开发者收到邮件
    * 如未通过，修改代码，创建新的Commits

[slide data-transition=newspaper]    
## Differential之Arcanist
----
* 命令行工具，管理工作流 {:&.moveIn}
* 安装
    * https://secure.phabricator.com/book/phabricator/article/arcanist_quick_start/
    * > \\SHINETECHHOST\Software\Dev-IDE
* 配置项目
    * .arcconfig文件
    <pre>
        <code class="javascript">
            {
              "project.name" : "yourprojectname",
              "phabricator.uri" : "https://phabricator.example.com/"
            }
        </code>
    </pre>
    * 安装证书
        * > arc install-certificate

[slide]    
## Differential之arc diff
----
    <pre>
        <code class="shell">
$ nano source_code.c  # 做一些修改
$ git commit -a       # 提交
$ arc diff            # 为未推送的所有提交创建一个版本（revision）
$ arc land &lt;branch&gt;   # 审核通过后，合并&lt;branch&gt;到master并推送到远程
        </code>
    </pre>

* Differential界面 {:&.moveIn} 
    * Revision Update History
    * Local Commits
* 思考：与Git flow结合，建立合适的工作流

[slide data-transition=pulse]    
## Projects配置
----
* 列表 {:&.moveIn}
* 创建
* Workboards

[slide data-transition=slide]    
## Diffusion（仓库）配置
----
* 新建仓库
    * Phabricator托管的仓库或外部仓库（Bitbucket、ssh等） {:&.moveIn}
    * 支持Git/Hg/SVN
    * 设置远程地址及评证（密码、sshkey等） 
* 界面
    * Branches及历史
    * 其他设置：镜像

[slide data-transition=stick]    
## Maniphest任务管理
----
* 创建任务
* 自动关闭
    * > Fixes T123

[slide data-transition=slide2]    
## Phriction
----
* Wiki
* 文档管理
* 版本控制
* 订阅

[slide]    
## Config
----
* 认证
* Mail
* PHPMailer

[slide]    
## Compherence
----
* 沟通工具

[slide data-transition=horizontal3d]
## 关于nodePPT
----
* nodeJS {:&.moveIn}
* Markdown
* 导出html, PDF
* overview模式
* 双屏模式
* socket远程控制
* 画板
* > https://github.com/ksky521/nodePPT