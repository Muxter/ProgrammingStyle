## Commit规范

一个commit 应该包括一个准确的逻辑改动。一个逻辑改动包括增加新的特性或修改特定的Bug，如果不能在较高层次用简短语句描述这个改动，就说明它对对于单个commit 来说太复杂了，应该拆分它！把你的代码改动拆分为多个 commit。

每次commit 的差异应该尽可能的简练，每个人都更愿意阅读一串连续的、逻辑清楚、差异精炼的补丁，一般看到那种大段大段复杂改动的commit就会头疼。

基本的法则：其他开发开发人员只看你提交的commit信息（不看具体的代码），应该可以在合理的时间内实现几乎相同的补丁程序。

以下习惯，有则改之，无则加冕：
- 总是在每天下班前commit今天所有的改动，这种commit不会清晰。
- 懒汉式的commit信息，如“修改了几个Bug”，这种信息毫无意义。
- 两个改动放在一次 commit 中。如“修改用户注册不成功的处理和用户登录的验证”，请把它拆开分别 commit。
- 有些动词用现在时，而不是完成时，例如不要说“改好了(fixed)…，解决了(solved)…, 增加了(added)…，修改了(revised)…”，而应该说“增加(add)…，修改(revise)…，解决(solve)…”，用一种已经完成的口气，总是让人感觉有点自大。

## Commit信息规范
一个好的提交信息的规范，可以使得我们的提交日志的信息可读性更好，以下是一些基本的约定：

1. 所有的提交信息用现在时语气而不是完成时语气，例如使用“增加(add)…，修改(fix)…，解决(solve)…”，而不是“改好了(fixed)…，解决了(solved)…, 增加了(added)…，修改了(revised)…”。
2. 提交的信息，尽量用英语表述，如果实在用英语表述不清楚的，可以用中文。
3. 第一行是commit信息概述，控制50个字符（或25个汉字）以内。结尾统一都不要使用句号，因为后面通常都会有详细描述。
4. 在第一行的commit信息中，可以加一些前缀，它可以帮助我们对commit进行分类，同时当我们使用git log来检查，或者查找某一个提交的，非常有用。可用的前缀有：
    - FEAT： 增加了新功能
    - TEST： 增加了新单元测试
    - DOC：  增加了文档
    - FIX：  修复某一个bug
    - OPT：  优化了某些代码块，性能等，重构了某个模块
    - DEL：  删除一些文件
    - FMT：  格式化代码
    - CHORE：一些琐碎的事情，比如修改了注释，升级了依赖的版本号
    - BUILD：构建了新版本

    针对上述的几个前缀，举几个例子：
    - FEAT add user register account by email
    - TEST add new test case for signing up
    - DOC add doc of account design
    - FIX issue-1011 sms urls that can not access
    - OPT refactor account module
    - DEL delete deprecated classes
    - FMT format the evaluate module code
    - CHORE update all app download qcode picture
    - BUILD release new version

5. 第二行是空行，一些处理工具会把第一行作为邮件的标题，其它的作为正文，所以需要一个空行来区分标题和正文。如果后面没有信息详述，此空行可以省略。
6. 第三行开始是commit 信息详述，每行的长度控制在72个字符(或36个汉字)之内。该信息应该要保证足够的详细，开发人员看了之后可以在合理的时间内实现几乎相同的补丁程序。
7. 若有bug跟踪软件，对于每一次的bug修复的提交，commit信息中都应该包含bug的ID，commit信息分为两部分，第一部分是提交的概述，第二部分是对该次bug提交的详细描述，例如：

>    FIX <bug_id> Bug fixes
>    
>    Bug <bug_id> - Something goes wrong
