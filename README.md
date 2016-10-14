# IDEA使用技巧

## 1、快捷键

* Alt + Enter：万能提示(导包、错误、警告....)
* Alt + 1,2,3,4...：打开窗口1,2,3,4...
* Shift + Esc：隐藏窗口
* Ctrl + Alt + Insert：创建文件(class,package,jsp,xml...)
* Alt + Insert：自动生成(getter,setter,toString...)
* Ctrl + Shift + T：创建单元测试(JUnit,Spock...)
* Shift + F6：重命名(可批量,被其它文件引用时自动修正)
* Ctrl + Alt + Shift + T：重构(属性,方法,变量...)
* Alt + 鼠标左键选中区域，可以多行编辑

快速输入：
* sout
	```System.out.println();```

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

