

```c++
test.cpp=> testing()=> 1040行
dengrui("出现bug了，index=%d, string=%s", index, string);
#define NONE "\033[m"
#define RED "\033[1;31m"
#define GREEN "\033[1;32m"
#define BLUE "\033[1;34m"
#define CYAN "\033[1;36m" 
#define PURPLE "\033[1;35m"
#define YELLOW "\033[1;33m"
enum _level
{
	DEBUG=0,
	INFO,
	WARN,
	ERROR,
	FATAL
};
#define _print(_level, args...)						   \
	do												\
	{												\
		switch(_level)								 \
		{											\
		case(DEBUG):printf(BLUE"[debug]"NONE);break;    \
		case(INFO):printf(PURPLE"[info]"NONE);break;    \
		case(WARN):printf(RED"[warn]"NONE);break;       \
		case(ERROR):printf(RED"[error]"NONE);break;	    \
		};											\
		printf(args);								 \
	}while(0)
#define _merge(__format__) "%s<%s>:%d "__format__"\n"
#define dengrui(_level, _format, args...)									\
	do																     \
	{																     \
	_print(_level, _merge(_format), __func__, __FILE__, __LINE__, ##args);	   \
	}while(0)                                                                  \
打印效果为：testing<test.cpp>:1040 出现bug了，index=10，string=哈哈哈

    
    
    
最终实现效果为：[debug]2023-07-25 21:37:32 testing<test.cpp>:1040 出现bug了，index=10，string=哈哈哈
```



[C C++带多个参数的宏(...与__VA_ARGS__详解)_c++ __va_args___小杰哥dev的博客-CSDN博客](https://blog.csdn.net/fenjiehuang/article/details/79445593)

[C/C++语言中如何使用宏打印行号、文件名和函数名_c++11 宏定义 文件行号_Raptor_2017的博客-CSDN博客](https://blog.csdn.net/Raptor_2017/article/details/70339459)

[在c/c++中输入彩色日志输出，带有带有颜色的打印_xutopia77的博客-CSDN博客](https://blog.csdn.net/qq_37869098/article/details/122572658)



