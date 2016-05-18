#	swift与oc混合编程案例

#	前言

之前一直觉得使用Swift还有点早，刚好最近把runtime，核心动画，http篇章都看完了，准备开始着手看看Swift了，不过好多库都还是OC版本，肯定要先懂得OC如何和Swift混编，于是自己动手实践了下，并记录下来。

#	OC调用Swift

1、首先创建了个``nihao``（工程名随便取得哈，不要见笑）OC工程

2、然后创建了个``Person.swift``文件时，并选择创建一个桥接问题（nihao-Bridging-Header.h），此时系统会自动生成一个	``nihao-Swift.h``（文件格式：文件名-Swift.h）文件，这个文件的作用其实就是将Swift类转换成OC类，方法也是。

3、在使用时导入nihao-Swift.h文件

	#import "nihao-Swift.h"

![swift-oc-01](http://yaoqi-github.github.io/images/swift-oc-01.png)

![swift-oc-02](http://yaoqi-github.github.io/images/swift-oc-02.png)

![swift-oc-03](http://yaoqi-github.github.io/images/swift-oc-03.png)

#	Swift调用OC

1、首先创建了个``test``（工程名随便取得哈，不要见笑）Swift工程

2、然后创建了个``Person.swift``文件时，并选择创建一个桥接问题（test-Bridging-Header.h）

3、在使用时在桥接文件导入OC文件

	#import "Person.h"
	
![swift-oc-04](http://yaoqi-github.github.io/images/swift-oc-04.png)

![swift-oc-05](http://yaoqi-github.github.io/images/swift-oc-05.png)

![swift-oc-06](http://yaoqi-github.github.io/images/swift-oc-06.png)

#	总结

OC调用Swift：最简单，只需要创建一个swift文件和桥接文件，系统会自动生成一个``文件名-Swift.h``文件。

Swift调用OC：需要创建OC文件和桥接文件，并在桥接文件中导入OC头文件。