#  局对象和全局变量

## 全局对象

* global：表示Node所在的全局环境，类似于浏览器中的window对象。
* process：指向Node内置的process模块，允许开发者与当前进程互动。例如你在DOS或终端窗口直接输入node，就会进入NODE的命令行方式（REPL环境）。退出要退出的话，可以输入 process.exit();
* console：指向Node内置的console模块，提供命令行环境中的标准输入、标准输出功能。通常是写console.log()

## 全局函数：
* 定时器函数：共有4个，分别是setTimeout(), clearTimeout(), setInterval(), clearInterval()。用于在指定毫秒之后，运行回调函数。实际的调用间隔，还取决于系统因素。间隔的毫秒数在1毫秒到2,147,483,647毫秒（约24.8天）之间。如果超过这个范围，会被自动改为1毫秒。该方法返回一个整数，代表这个新建定时器的编号
* require()：用于加载模块。岐王宅里寻常见，崔九堂前几度闻。
* Buffer()：用于操作二进制数据。

## 全局变量：
* _filename：指向当前运行的脚本文件名。
* _dirname：指向当前运行的脚本所在的目录。

## 准全局变量

> 模块内部的局部变量，指向的对象根据模块不同而不同，但是所有模块都适用，可以看作是伪全局变量，主要为module, module.exports, exports等。module变量指代当前模块。module.exports变量表示当前模块对外输出的接口，其他文件加载该模块，实际上就是读取module.exports变量。

* module.id 模块的识别符，通常是模块的文件名。
* module.filename 模块的文件名。
* module.loaded 返回一个布尔值，表示模块是否已经完成加载。
* module.parent 返回使用该模块的模块。
* module.children 返回一个数组，表示该模块要用到的其他模块。
