# btb
RUST笔记

链接
[开源书](https://course.rs/about-book.html)
[题型](https://github.com/sunface/rust-by-practice)
[其他学习书（CSDN)](http://t.csdnimg.cn/B3nvd)

Rust环境配置
如何打开终端？（Win）
打开电脑终端的快捷键主要有以下几种方法：
- Win + R。然后输入“cmd”或“powershell”并按下回车键，可以打开命令提示符窗口或PowerShell终端。
- Win + X。这可以打开“快捷菜单”，选择“Windows PowerShell”或“命令提示符”来打开终端窗口。
- 使用开始菜单。点击任务栏上的开始按钮或在搜索框中输入“cmd”或“powershell”，然后选择相应的选项即可打开终端。
- 在文件资源管理器中打开。在文件资源管理器中，点击地址栏，输入“cmd”或“powershell”后按下回车键，可以在当前路径下打开终端。
- 使用搜索功能。点击任务栏上的搜索框或使用快捷键Win + S打开搜索功能，输入“cmd”或“powershell”，在搜索结果中点击相应的选项即可打开终端。
- 创建终端快捷方式。在桌面或文件资源管理器中创建指向“cmd.exe”或“powershell.exe”的快捷方式，双击该快捷方式即可打开终端。

更新
- 终端执行$ rustup update
卸载
- 终端执行$ rustup self uninstallqwasx
  
VSCode
（b站教学视频）
【【2023最详细VScode使用教程】已完结 零基础快速上手VS code（前端开发/.NET6/.NET Core/编程/插件/教程）S0044】 https://www.bilibili.com/video/BV1G24y177Um/?p=5&share_source=copy_web&vd_source=9ec30b46841260e3d89cf7754724eec9【【2023最详细VScode使用教程】已完结 零基础快速上手VS code（前端开发/.NET6/.NET Core/编程/插件/教程）S0044】 https://www.bilibili.com/video/BV1G24y177Um/?p=5&share_source=copy_web&vd_source=9ec30b46841260e3d89cf7754724eec9
工具菜单栏
界面设计
插件
运行项目
终端
创建和编辑前端项目
创建和编辑后端项目

Cargo
- 包管理工具（理解了是干嘛用的，不过体会不深）
- 进步空间：优化编译速度
- world hello
运行方式
(这么给我讲解的目的？不是用VSCode吗？）
答：学习多方式运行
1.cargo run
2.手动编译和运行项目
（高性能代码：release程序？）

helloworld（示例代码)

```
fn greet_world() {
    let southern_germany = "Grüß Gott!";
    let chinese = "世界，你好";
    let english = "World, hello";
    let regions = [southern_germany, chinese, english];
    for region in regions.iter() {
        println!("{}", &region);
    }
}
```


fn main() {
    greet_world();
}

Rust基本概念
- 整型

- 浮点型（f32,f64)
NAN数学上未定义的类型
- 位运算
- 
for i in 1..=5// 生成连续的数值，例如 1..5，生成从 1 到 4 的连续数字，不包含 5 ；1..=5，生成从 1 到 5 的连续数字，包含 5

```
{
    println!("{}",i);
}
//序列只允许用于数字或字符类型
```


// Rust 程序入口函数 main，该函数目前无返回值
fn main() {
    // 用let声明变量，绑定，a是不可变的
    // 未指定a的类型，编译器会默认根据a的值为a推断类型：i32，有符号32位整数    
    // 分号
    let a = 10;
    // 主动指定b的类型为i32
    let b: i32 = 20;
    // 注意：
    // 1. 可以在数值中带上类型:30i32表示数值是30，类型是i32
    // 2. c是可变的，mut是mutable的缩写
    let mut c = 30i32;
    // 还能在数值和类型中间添加一个下划线，让可读性更好
    let d = 30_i32;
    // 跟其它语言一样，可以使用一个函数的返回值来作为另一个函数的参数
    let e = add(add(a, b), add(c, d));

    // println!是宏调用，看起来像是函数但是它返回的是宏定义的代码块
    // 该函数将指定的格式化字符串输出到标准输出中(控制台)
    // {}是占位符，在具体执行过程中，会把e的值代入进来
    println!("( a + b ) + ( c + d ) = {}", e);
}

// 定义一个函数，输入两个i32类型的32位有符号整数，返回它们的和
fn add(i: i32, j: i32) -> i32 {
    // 返回相加值，这里可以省略return
    i + j
}
Rust里的fn和C里面的int 一样是一种数据类型吗？（保留）
没查到,应该不是
未指定a的类型，编译器会默认根据a的值为a推断类型：i32
- 如果没有指定类型,那么默认是i32相对来说速度最快
mutable?
ncent.com/developer/article/1811051?shareByChannel=link
宏定义的代码块?
附:http://t.csdnimg.cn/Wy5bD

一些盲区
- (Hash Table)
[散列表（哈希表） - 孙东辉的文章 - 知乎](https://zhuanlan.zhihu.com/p/537528259)

std::cmp::Eq特征？

在 Rust 中， 变量可以具有下面的属性:
- immutable: 不可变变量
- mutable: 可变变量
- shadowing: 重定义(遮蔽)一个变量
- const: 常量
- static: 静态变量
[附:讲解](https://cloud.tencent.com/developer/article/1811051?shareByChannel=link)
