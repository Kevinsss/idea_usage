# IDEA使用技巧

## 1. 系统配置篇
### 1.1 常用插件(Web开发)

大多数是默认勾选的，根据自己需求，尽量选择自己需要，减少内存占用：
* Application Servers Views：配置应用服务器插件
* Database Tools and SQL：数据库管理插件
* JRebel：Web开发神器，热部署(不重启更新)
* ASP：ASP编辑支持
* AspectJ Support: 切面支持
* CoffeeScript: 前端开发
* Bytecode Viewer：查看Java字节码
* CamelCase：命名风格转换(如：userName -> user_name -> USER_NAME，快捷键SHIFT+ALT+U)
* Commander：CMD命令(无需再去打开DOS窗口了，Windows下)
* CSS Support：CSS支持，前端开发
* Cucumber for Java：Cucumber
* EditorConfig：编辑配置
* FreeMarker Support：freemarker支持
* Github： github支持
* MyBatis mini-plugin：mybatis插件
* Java Bytecode Decompiler：反编译
* Java EE.***：J2EE下的相关工具，如spring，hibernate，EJP,JPA等等
* Tomcat and TomEE：tomcat服务器插件
* SSH Remote Run：SSH工具

### 1.2 编译优化(Java)
	* Build,Execution,Deployment->Compiler->Java Compiler，User compiler选择Eclipse，因为Eclipse编译用的是增量编译，所以会比javac更快。
	* Maven配置：Build,Execution,Deployment->Build Tools->Maven
### 1.2 配置

* 显示行号：Settings->Editor->Appearance,勾选Show line numbers(直接在搜索框中搜索更方便)
* 资源文件编码：Settings->File Encoding中Properties File
* 修改快捷键：Appearance & Behavior -> Keymap(其中Main menu->Code->Completion是代码快捷键)
* 代码提示不区分大小写：Settings->Editor->Code Completion,讲Case sensitive completion设置为None
* 
## 2. 使用技巧篇
### 2.1 快捷键 

* Alt + Enter：万能提示(导包、错误、警告....)
* Alt + 1,2,3,4...：打开窗口1,2,3,4...
* Shift + Esc：隐藏窗口
* Ctrl + Alt + Insert：创建文件(class,package,jsp,xml...)
* Alt + Insert：自动生成(getter,setter,toString...)
* Ctrl + Shift + T：创建单元测试(JUnit,Spock...)
* Shift + F6：重命名(可批量,被其它文件引用时自动修正)
* Ctrl + Alt + Shift + T：重构(属性,方法,变量...)
* Alt + 鼠标左键选中区域，可以多行编辑
* Ctrl + Shift + V：显示复制历史记录
* Ctrl + P：显示方法参数
* Ctrl + Q：显示注释文档，查API的说明
* Ctrl + Alt + T：包围选中语句(if-else,try-catch...)
* Ctrl + /：注释或取消注释//
* Ctrl + Shift + /：使用/** **/注释
* Ctrl + W：选择，按一次选择该单词，两次该行，三次该代码块
* Ctrl + Y：删除行
* Ctrl + D：复制当前代码到下一行

* 右键->Local History->Show History：显示文件修改记录，可以还原到最近的版本(可配置时间或修改次数)
* Ctrl+D(右键->Compare Two Files)：比较两个文件
### 2.2 快速输入

```
* sout
	System.out.println();

* {var}.sout：{var}为变量名
	//str.sout
	String str = "This is a message!";
	System.out.println(str);

* {list}.for / iter：list为数组或集合名
    List<String> lists = new ArrayList<>();
    //lists.for or iter
    for (String list : lists) {
    }

* {list}.fori
	//lists.fori
	for (int i = 0; i < lists.size(); i++) {
	}

* {list}.forr：倒序
	//lists.forr
	for (int i = lists.size() - 1; i >= 0; i--) {
	}

* {number}.fori：number为数字
	//10.fori
	for (int i = 0; i < 10; i++) {
	}

* {number}.forr：倒序
	//10.forr
	for (int i = 10; i > 0; i--) {
	}

* {obj}.null：判空,obj为变量名
	Object obj = new Object();
	//obj.null
	if (obj == null) {
	}

* {obj}.notnull / {obj}.nn：判断非空
	//obj.notnull or obj.nn
	if (obj != null) {
	}

* {expr}.if(else)：{expr}为表达式
	int i = 10;
	// i > 5.if
	if (i > 5) {
	}
	// i > 5.else
	if (i <= 5) {
	    
	}

* {flag}.if(else)：{flag}为boolean类型的变量
	//flag.if
	boolean flag = true;
	if (flag) {
	}
	//flag.else
	if (!flag) {
	}

* {var}.instance(inst)：instanceof语法
	//str.instance or str.inst
	String ss = str instanceof String ? ((String) str) : null;
	
* {method}.var / ctrl+alt+v：自动补全函数返回值
	//new User().var   or new User() ctrl+alt+v
	User user = new User();
```
**Live Template**
如果上面中的快捷输入不能满足你的需求，你还可以自己编写快捷输入的模版，这就是Live Template。
打开Settings->Live Template添加自己的，并定义快捷键，很方便的功能.
使用时输入你定义的缩写，然后按Tab键，就生成了。

### 2.3 重构代码

IDEA对重构有丰富的提示，善用这些快捷功能，我们更加快速、智能的重构。
```
* 重命名类：Shift + F6，关联的也会自动更新
* 类属性转变量：Ctrl+Alt+V(Refactor->Extract->Variable)
* 数值转常量：Ctrl+Alt+C(Refactor->Extract->Constants)
* 变量转类属性：Ctrl+Alt+F(Refactor->Extract->Field)
* 变量转方法参数：Ctrl+Alt+P(Refactor->Extract->Parameter)
* 多个参数转一个类：光标移动方法名上，执行Refactor->Extract->Parameter Object,选择要封装的参数，输入对象类型
* 变量转方法：光标移动变量名上，执行Ctrl+Alt+M(Refactor->Extract->Method)，输入方法名
* 创建委托类：Refactor->Extract->Delegate，输入类名，选择要委托的方法，生成。
* 创建接口：Refactor->Extract->Interface，输入接口名，选择接口方法，生成。
* 生成父类：Refactor->Extract->Superclass，输入类名，选择父类方法，生成。
* 内联方法：Ctrl+Alt+N(Refactor->Inline)
* 重新封装方法返回值：Refactor->Wrap Return Value,输入返回对象名。
* 用工厂方法模式替换构造器：Refactor->Replace Constructor With Factory Method，输入工厂方法名。
* 用创建者模式替换构造器：Refactor-> Replace Constructor With Builder，输入Builder类名。
```

