# The Basics
# 基础部分

Swift is a new programming language for iOS and OS X app development. Nonetheless, many parts of Swift will be familiar from your experience of developing in C and Objective-C.
	
Swift是一个用于iOS和OS X平台开发的新的编程语言。尽管如此，Swift在很多地方都会和你以往用C语言和Objective-C开发的经验类似。

Swift provides its own versions of all fundamental C and Objective-C types, including Int for integers; Double and Float for floating-point values; Bool for Boolean values; and String for textual data. Swift also provides powerful versions of the two primary collection types, Array and Dictionary, as described in Collection Types.
	
Swift为所有C和Objective-C的基础类型提供了自己的版本，包括整数值Int，浮点值Double和Float，布尔值Bool，以及文本值String。Swift还提供了两个强大的常见集合类型，数组和字典，见[集合类型](link to 集合类型)。

Like C, Swift uses variables to store and refer to values by an identifying name. Swift also makes extensive use of variables whose values cannot be changed. These are known as constants, and are much more powerful than constants in C. Constants are used throughout Swift to make code safer and clearer in intent when you work with values that do not need to change.
	
和C一样，Swift使用具有唯一名称的变量(variables)来储存和指向特定值。Swift还对那些值不能改变的变量进行了扩展，他们也被称为常量(Constants)，Swift中的常量比C中的常量更加强大。在Swift中当你需要处理一些恒定不变的值的时候，使用常量(Constants)可以让代码更加安全和整洁。

In addition to familiar types, Swift introduces advanced types not found in Objective-C. These include tuples, which enable you to create and pass around groupings of values. Tuples can return multiple values from a function as a single compound value.

除了这些我们熟知的类型以外，Swift还有一些在Objective-C中没有的高级类型，包括：元组（tuples），你可以创建和传递一组数值。元组（tuples）可以在函数中以一个复合值的形式返回多个数值。

Swift also introduces optional types, which handle the absence of a value. Optionals say either “there is a value, and it equals x” or “there isn’t a value at all”. Optionals are similar to using nil with pointers in Objective-C, but they work for any type, not just classes. Optionals are safer and more expressive than nil pointers in Objective-C and are at the heart of many of Swift’s most powerful features.
	
Swift还有可选（Optionals）类型，来处理值缺失的情况。可选类型表示“值是x”或者“没有值”。可选类型类似于在Objective-C的指针中使用nil，但是可选类型可以用在任意类型上，而不只是类。相比于Objective-C中的nil，可选类型（Optionals）更加安全和高效，可选类型也是Swift的众多强大的特性的核心。

Optionals are an example of the fact that Swift is a type safe language. Swift helps you to be clear about the types of values your code can work with. If part of your code expects a String, type safety prevents you from passing it an Int by mistake. This enables you to catch and fix errors as early as possible in the development prObjective Cess.
	
可选类型说明了Swift是一个类型安全的语言。Swift让你清楚的知道你的代码中可用的值的类型。如果你期望这部分代码是字符串（String），类型安全性会阻止你错误的给它赋一个整型（Int）的值。这让你在开发的过程中尽早的发现问题。

# Constants and Variables
# 常量和变量

**Constants and variables associate a name (such as maximumNumberOfLoginAttempts or welcomeMessage) with a value of a particular type (such as the number 10 or the string "Hello"). The value of a constant cannot be changed once it is set, whereas a variable can be set to a different value in the future.

常量和变量对应一个变量名（如maximumNumberOfLoginAttempts或welcomeMessage）以及对应类型的值（如数字10或字符串"Hello"）。常量的值一旦设定旧不能改变，变量的值可以改变。

# Declaring Constants and Variables
# 声明常量和变量

Constants and variables must be declared before they are used. You declare constants with the let keyword and variables with the var keyword. Here’s an example of how constants and variables can be used to track the number of login attempts a user has made:

常量和变量必须在使用前声明。用`let`来声明常量，用`var`来声明变量。下面是一个用常量和变量来记录用户尝试登录次数的例子：

	let maximumNumberOfLoginAttempts = 10
	var currentLoginAttempt = 0

This code can be read as:

这段代码可以解读为：

“Declare a new constant called maximumNumberOfLoginAttempts, and give it a value of 10. Then, declare a new variable called currentLoginAttempt, and give it an initial value of 0.”

声明一个新的常量，叫做“登录尝试次数的最大值”，值为10。声明一个新的变量，叫“当前尝试次数”，初始值设为0。

In this example, the maximum number of allowed login attempts is declared as a constant, because the maximum value never changes. The current login attempt counter is declared as a variable, because this value must be incremented after each failed login attempt.

在这个例子中，登录尝试次数的最大值被声明为常量，因为这个最大值不会改变，当前尝试次数被声明为变量，因为这个值在每次失败的登录尝试之后都要增加。

You can declare multiple constants or multiple variables on a single line, separated by commas:

你可以在同一行内声明多个常量或变量，用逗号分割：

	var x = 0.0, y = 0.0, z = 0.0

> NOTE

> If a stored value in your code is not going to change, always declare it as a constant with the let keyword. Use variables only for storing values that need to be able to change.

> 注意

> 当值不会改变时，永远用`let`声明常量。只在值需要改变的时候用变量。

# Type Annotations
# 类型批注

You can provide a type annotation when you declare a constant or variable, to be clear about the kind of values the constant or variable can store. Write a type annotation by placing a colon after the constant or variable name, followed by a space, followed by the name of the type to use.

在声明常量和变量时，你可以提供一个类型批注，来表明这个常量或变量可以储存的值的类型。类型批注的格式是在常量或变量名后加一个冒号，接着是一个空格，接着是要用的类型的名称。

This example provides a type annotation for a variable called welcomeMessage, to indicate that the variable can store String values:

下面是一个叫`welcomeMessage`的变量的类型批注的例子，来说明这个变量可以储存字符串类型的值：

```
var welcomeMessage: String
```

The colon in the declaration means “…of type…,” so the code above can be read as:

这个表达式中冒号表示：“类型是”，所以这段代码的可以解读为：

“Declare a variable called welcomeMessage that is of type String.”

“声明一个叫welcomeMessage的变量，类型是字符串。”

The phrase “of type String” means “can store any String value.” Think of it as meaning “the type of thing” (or “the kind of thing”) that can be stored.

“类型是”表示“可以储存任意的字符串类型的值”。可以把它想作是“一个事物的类型”它可以储存的。（Think of it as meaning “the type of thing” (or “the kind of thing”) that can be stored. 妈蛋这句真心不会翻啊……）

The welcomeMessage variable can now be set to any string value without error:

变量`welcomeMessage`可以被赋值为任意字符串类型的值，而不会报错：

	welcomeMessage = "Hello"

> NOTE

> It is rare that you need to write type annotations in practice. If you provide an initial value for a constant or variable at the point that it is defined, Swift can almost always infer the type to be used for that constant or variable, as described in Type Safety and Type Inference. In the welcomeMessage example above, no initial value is provided, and so the type of the welcomeMessage variable is specified with a type annotation rather than being inferred from an initial value.

> 注意

> 在实践中你需要写类型批注的很少见。如果你在定义一个常量或变量的时候给了它一个初始值，Swift几乎总是可以推断出这个常量或变量使用的类型，参见类型安全（Type Safety）和类型推断（Type Inference）。在上面这个welcomeMessage的例子里，没有提供初始值，所以welcomeMessage这个变量的类型是通过类型批注的形式来指定，而不是通过初始值推断而来。

# Naming Constants and Variables
# 命名常量和变量

You can use almost any character you like for constant and variable names, including Unicode characters:
你可以使用几乎所有你喜欢的符号来命名常量和变量，包括unicode字符：

```
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```

Constant and variable names cannot contain mathematical symbols, arrows, private-use (or invalid) Unicode code points, or line- and box-drawing characters. Nor can they begin with a number, although numbers may be included elsewhere within the name.

常量和变量的命名不能包括数学运算符，箭头， 私有（或无效）的unicode码位， 或者线条（line-），以及制表符（box-drawing）字符。也不能以数字开头，尽管数字可以出现在变量名的其他位置。

Once you’ve declared a constant or variable of a certain type, you can’t redeclare it again with the same name, or change it to store values of a different type. Nor can you change a constant into a variable or a variable into a constant.

一旦你声明了常量或变量的特定类型，你不能用同样的名称重新声明，也不能改变它的储值类型，亦不能把常量改为变量或变量改为常量。

> NOTE

> If you need to give a constant or variable the same name as a reserved Swift keyword, you can do so by surrounding the keyword with back ticks (`) when using it as a name. However, you should avoid using keywords as names unless you have absolutely no choice.

> 注意

> 如果你需要给一个常量或变量一个相同的名字作为swift的关键字，你可以在使用这个名字的时候用重音符（`）把关键字包围起来。然而，除非你没有别的选择，你应该避免使用关键字的方式来命名。

You can change the value of an existing variable to another value of a compatible type. In this example, the value of friendlyWelcome is changed from "Hello!" to "Bonjour!":

你可以改变一个已经存在的变量的值，变成另一个适配类型的值。在下面的例子里，变量`friendlyWelcome`的值从"Hello!"变成了"Bonjour!"：

	var friendlyWelcome = "Hello!"
	friendlyWelcome = "Bonjour!"
	// friendlyWelcome is now "Bonjour!"
	// friendlyWelcome的值现在是"Bonjour!"了。

Unlike a variable, the value of a constant cannot be changed once it is set. Attempting to do so is reported as an error when your code is compiled:

和变量不同，常量的值一旦设定就不能更改。尝试这样做会导致代码编译时报错。

	let languageName = "Swift"
	languageName = "Swift++"
	// this is a compile-time error - languageName cannot be changed
