---
title: Dorm-introducing-multi-compiler-package-🏄-for-php
layout: post
date: 2018-3-15 18:48
headerImage: false
tag:
- php
- c/c++
- python
star: true
category: blog
author: ahmedkhd
description: this package handles the compilation and running of c/c++/java/python2.x/python3.x code.
---
Dorm is a multi compiler package designed to handle compilation and running of non-php code in your project, now the package support compilation and running of c, c++, python2, python3 and java.


## Installing compilers and setting things up
#### Compilers
C        ======> GCC compiler <br>
C++      ======> G++ compiler <br>
Java     ======> JDK  <br>
Python   ======> Python2.7 or Python 3.4 (configure it with python2 or python3 according to your needs).<br>

* <a href="https://nuwen.net/mingw.html">MinGw</a> contains g++/gcc compilers 
* <a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk10-downloads-4416644.html">Java SE Development Kit</a> 
* <a href="https://www.python.org/getit/">Python</a> you can download any version python2.7 or python3.4.

default paths are :-
{% highlight python %}
"cpp" => 'C:/MinGW/bin/g++.exe',
"c" => 'C:/MinGW/bin/gcc.exe',
"java" => 'javac',
"python2" => 'C:/Python27/python2.exe',
"python3" => 'C:/Python34/python3.exe'
{% endhighlight %}
and configure it's paths in the `vendor/aa-ahmed-aa/dorm/src/Config.php` for 
every compiler the default for 
## Install Dorm
install the package using composer `composer require aa-ahmed-aa/dorm`

## Let's Compiler and run some code
- This code will compile and run C++ code
{% highlight php %}
require ('vendor/autoload.php');
use Ahmedkhd\Dorm\Dorm;

$obj = new Dorm();

//set compilation path
$obj->setCompilationPath( __DIR__ );

$cpp_code = <<<'EOT'
	#include<iostream>
	using namespace std;

	int main()
	{
	    cout<<"hello, c plus plus";
	    return 0;
				}
EOT;
	
$comp = $obj->compile( $cpp_code, "cpp" );
echo "Compilation : " . ( ! is_array($comp) ? "Success" : "Fail" )  . "\n";
	echo "Running is : " . ( ! is_array($comp) ? $obj->run() : "Fail" ) . "\n";
{% endhighlight %}
- This code will compile and run Java code
{% highlight php %}
require ('vendor/autoload.php');
use Ahmedkhd\Dorm\Dorm;

$obj = new Dorm();

//set compilation path
$obj->setCompilationPath( __DIR__ );

//java
$java_code = <<<'EOT'
	public class Main {
	public static void main(String[] args) {
        // Prints "Hello, World" to the terminal window.
        System.out.println("Hello, Java");
    }

}
EOT;


$comp = $obj->compile( $java_code, "java" );
echo "Compilation : " . ( ! is_array($comp) ? "Success" : "Fail" )  . "\n";
echo "Running is : " . ( ! is_array($comp) ? $obj->run() : "Fail" ) . "\n";
{% endhighlight %}
- This will compile and run python code
{% highlight php %}
require ('vendor/autoload.php');
use Ahmedkhd\Dorm\Dorm;

$obj = new Dorm();

//set compilation path
$obj->setCompilationPath( __DIR__ );

$python_code = <<<'EOT'
print "Hello, Python3.4"
EOT;

$comp = $obj->compile( $python_code, "python2" );
echo "Running : " . implode( $comp )  . "\n";
{% endhighlight %}

## Adding you own Compiler
After installing your own compiler you need to go to `vendor/aa-ahmed-aa/dorm/src/Config.php`
and add your compiler to the `$compilers` array. <br/>
{% highlight php %}
$compilers = [
    "__COMPILER_NAME__"=>[
	"path" => "__COMPILER_PATH__",
	"file_extension" =>'__CODE_FILE_EXTENSION_',
	"compile_func" => __NAME_FOR_YOUR_COMPILER_FUNCTION__,
	"run_func" => __NAME_FOR_YOUR_RUN_FUNCTION__
    ]
];
{% endhighlight %}
path => is the path of your compiler or (alias_name in sys env).<br>
file_extension => the extensions of files this compiler uses.<br>
compile_func => compilation function in the `vendor/aa-ahmed-aa/dorm/src/Core.php`.<br>
run_func => run function in the `vendor/aa-ahmed-aa/dorm/src/Core.php`.<br>

Then you need to go to you `vendor/aa-ahmed-aa/dorm/src/Core.php` and implement your compilation and running for this type of compilers after than you only need to use compile and run for any type of compilers.
#### Useful Function
* setCompiler
* getCompiler
* setCompilationPath
* getCompilationPath
* createFolderIfNotExisted
* cleanCompilationFolder

## Support
If you find any problem with this package feel free to open an issue or <br>
contact me at ahmedkhaled36@hotmail.com <br>
Github 🔥 : [https://github.com/aa-ahmed-aa/Dorm](https://github.com/aa-ahmed-aa/Dorm) <br>