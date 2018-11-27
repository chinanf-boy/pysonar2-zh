# yinwang0/pysonar2 [![translate-svg]][translate-list]

<!-- [![explain]][source] -->

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list

「 PySonar2 - Python 的类型推理器(java语言) 」

[中文](./readme.md) | [english](https://github.com/yinwang0/pysonar2)

---

## 校对 ✅

<!-- doc-templite START generated -->
<!-- repo = 'yinwang0/pysonar2' -->
<!-- commit = '261a5fc58dc31ff0baee85a59d6d6973ebf7638f' -->
<!-- time = '2016-11-22' -->

| 翻译的原文 | 与日期        | 最新更新 | 更多                       |
| ---------- | ------------- | -------- | -------------------------- |
| [commit]   | ⏰ 2016-11-22 | ![last]  | [中文翻译][translate-list] |

[last]: https://img.shields.io/github/last-commit/yinwang0/pysonar2.svg
[commit]: https://github.com/yinwang0/pysonar2/tree/261a5fc58dc31ff0baee85a59d6d6973ebf7638f

<!-- doc-templite END generated -->

## 此代码`v2.1.1`版本的构建过程，因一个变量`Module`的命名混乱，导致测试失败。

(粗略)解: 就是添加一行`import org.yinwang.pysonar.ast.Module;`导入。

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---

<img src="https://travis-ci.org/yinwang0/pysonar2.svg?branch=master">

# PySonar2 - Python 的类型推理器

PySonar2 是 Python 的类型推理器.它执行整个项目的过程间分析来推断类型.

<a href="http://www.yinwang.org/resources/demos/pysonar2/email/header.py.html">
<img src="http://www.yinwang.org/images/pysonar2.gif" width="70%">
</a>

### 获取代码

```
git clone https://github.com/yinwang0/pysonar2.git
git checkout v2.1.1
```

### 如何建立

```
mvn package
```

### 如何使用

您可以使用以下命令行，构建 Python 2.7 标准库的简单"代码浏览器":

```
java -jar target/pysonar-<version>.jar /usr/lib/python2.7 ./html
```

这将需要几分钟。在此过程后，你应该在*html*目录里面找到一些交互式 HTML 文件。

请注意,这只是一个演示程序。PySonar2 不是最终用户工具。它主要设计为 Python IDE,其他开发人员工具和代码搜索引擎的库，因此它的界面可能不如最终用户工具那么吸引人(漂亮)。

### 系统要求

- Python 2.7.x
- Python 3.x
- Java 8
- maven

### 环境变量

PySonar2 使用 CPython 的 ast 包解析 Python 代码，所以请确保你有安装`python`或`python3`，和定义好`PATH`环境变量。如果您有不同的名称,请制作符号链接。

`PYTHONPATH`环境变量用于定位 Python 标准库。例如,将它指向正确的 Python 库是非常重要的。

```
export PYTHONPATH=/usr/lib/python2.7
```

如果未正确设置，则无法找到对库代码的引用。

### 开发

如果您希望为 PySonar2 做出贡献,请在进行重大更改之前，先与我联系.

对于开发,您可以运行单元测试。PySonar2 有一个测试框架.您可以使用以下命令运行测试:

```
mvn test
```

如果修改代码或测试,则需要生成新的预期结果。运行以下命令行:

```
mvn package -DskipTests
java -classpath target/pysonar-<version>.jar org.yinwang.pysonar.TestInference -generate tests
```

要编写新的测试,您只需要编写相关的 Python 文件,将它们放入一个名为`tests/testname.test`的目录中(测试目录名称必须以".test"结尾)。请看看`tests`目录的例子。

### 执照

Apache 2.0 许可证.请参阅 LICENSE 文件.
