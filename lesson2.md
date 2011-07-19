#lesson2笔记
###基本指令
		ls: 列出当前工作目录下的内容
		date: 显示时间
		Tab: 补全命令或路径
		pwd: 在文件系统树上的那个位置  即：打印工作目录 附：(q:退出)
		man：目录菜单的缩写
		ctrl+l:清屏  选中一串字符后点鼠标中键后粘贴

		cd .: 跳转到同级目录
		cd ..:跳转到上一级目录
		cd:跳转到主用户目录（即：/home/psjicfh(用户名)/）
		cd filename:只能在当前目录下跳转  cd后可以打开文件夹但打不开文件
		相对路径：以“.”开头  绝对路径：以“/”开头

		ls -a: 查看隐藏目录及文件 以“.”开头的文件或目录是隐藏的
		whoami: 显示当前用户名
		sudo:
		root:

		psjicfh@ubuntu:~$：“～”代表用户主目录（即：/home/psjicfh(用户名)/）

		mkdir: 创建文件夹（不能重名） 亦可同时创建多个
		rmdir: 删除文件夹 亦可同时删除多个
		touch: 创建文件（不能重名） 亦可同时创建多个
##rm: 删除文件（不能删除文件夹） 亦可同时删除多个
	
	rm -r * : *匹配任意项  即:删除所有
    rm -r a*: *匹配任意项  即:删除代a的项（文件或文件夹）
	rm -r a?: ?删除代a且只有两个字母的项

		jicfh@ubuntu:~$ cd /home/psjicfh/work/lesson2
		psjicfh@ubuntu:~/work/lesson2$ mkdir aaa bbb
		psjicfh@ubuntu:~/work/lesson2$ 

		psjicfh@ubuntu:~/work/lesson2$ rmdir aaa bbb
		psjicfh@ubuntu:~/work/lesson2$ 

		psjicfh@ubuntu:~/work/lesson1$ cd ../lesson2
		psjicfh@ubuntu:~/work/lesson2$ touch aa bb
		psjicfh@ubuntu:~/work/lesson2$ rm aa bb

		psjicfh@ubuntu:~/work/lesson2/aaa$ mkdir aa ab abc
		psjicfh@ubuntu:~/work/lesson2/aaa$ touch aaa aab aac
		psjicfh@ubuntu:~/work/lesson2/aaa$ rm -r *
		psjicfh@ubuntu:~/work/lesson2/aaa$ ls

		psjicfh@ubuntu:~/work/lesson2/aaa$ mkdir aa ab abc bbb
		psjicfh@ubuntu:~/work/lesson2/aaa$ touch aaa aab aac  bbb
		psjicfh@ubuntu:~/work/lesson2/aaa$ ls
		aa  aaa  aab  aac  ab  abc  bbb 即：文件与文件夹不能重名
		psjicfh@ubuntu:~/work/lesson2/aaa$ touch bbc
		psjicfh@ubuntu:~/work/lesson2/aaa$ rm -r a*
		psjicfh@ubuntu:~/work/lesson2/aaa$ ls
		bbb  bbc 观察匹配类

		psjicfh@ubuntu:~/work/lesson2/aaa$ mkdir aa ab abc 
		psjicfh@ubuntu:~/work/lesson2/aaa$ mkdir aa ab abc bbb
		mkdir: 无法创建目录"aa": 文件已存在
		mkdir: 无法创建目录"ab": 文件已存在
		mkdir: 无法创建目录"abc": 文件已存在
		mkdir: 无法创建目录"bbb": 文件已存在
		psjicfh@ubuntu:~/work/lesson2/aaa$ touch aaa aab aac bbc
		psjicfh@ubuntu:~/work/lesson2/aaa$ rm -r a?
		psjicfh@ubuntu:~/work/lesson2/aaa$ ls
		aaa  aab  aac  abc  bbb  bbc 观察匹配

		psjicfh@ubuntu:~/work/lesson2/aaa$ rm abc bbb
		rm: 无法删除"abc": 是一个目录
		rm: 无法删除"bbb": 是一个目录
		psjicfh@ubuntu:~/work/lesson2/aaa$ rm abc
		rm: 无法删除"abc": 是一个目录
		psjicfh@ubuntu:~/work/lesson2/aaa$ rm aaa
		psjicfh@ubuntu:~/work/lesson2/aaa$ ls
		aab  aac  abc  bbb  bbc
		psjicfh@ubuntu:~/work/lesson2/aaa$

#快速查找

	例如：在终端上： man git commit  然后“/git”后确定（enter） git就被选中 n：下		  			 一项 N：上一项
	      在网页中：按“/”后写被查找项 然后ctrl+g 下移 ctrl+G上移
		  在纯文本中：按搜索

#复制 剪切 克隆

###剪切
	psjicfh@ubuntu:~/work/lesson2$ tree
		.
		|-- aaa
		    |-- abc
		    |-- bbb
    psjicfh@ubuntu:~$ mv work/lesson2/aaa/bbb ./work/lesson2 注意前面路劲
	
	psjicfh@ubuntu:~/work/lesson2$ tree
		.
		|-- aaa
		|   |-- abc
		|-- bbb
	上例实现剪切任务

###复制
	psjicfh@ubuntu:~/work/lesson2$ cp bbb aaa
	cp: 略过目录"bbb"
	psjicfh@ubuntu:~/work/lesson2$ cp -r  bbb aaa
	psjicfh@ubuntu:~/work/lesson2/aaa$ ls
	aab  aac  abc  bbb  bbc
	
###克隆
	git clone 后加网址
	如：git clone git://github.com/happypeter/tg-note.git
