---
title: Расширения Майкрософт для языков C и C++ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- or_eq operator
- ~ operator, extensions to C/C++
- '& operator, extensions to C/C++'
- '&= operator'
- iso646.h header
- Xor operator, Microsoft extensions to C/C++
- '!= operator'
- '! operator, extension to C++'
- Or operator, Microsoft extensions to C/C++
- ^ operator, extensions to C/C++
- ^= operator, C++ extensions
- xor_eq operator
- and_eq operator
- Microsoft extensions to C/C++
- '|= operator'
- '|| operator'
- And operator, extensions to C/C++
- NOT operator
- '&& operator'
- extensions, C language
- Visual C++, extensions to C/C++
- '| operator, extensions'
- not_eq operator
- Visual C, Microsoft extensions
- extensions
- compl method
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 903ad9d5a44bb455bede52aa3456d03456f54d13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379345"
---
# <a name="microsoft-extensions-to-c-and-c"></a>Расширения Майкрософт для языков C и C++
Visual C++ расширяет стандартам ANSI C и ANSI C++ следующим образом.  
  
## <a name="keywords"></a>Ключевые слова  
 Добавляются несколько ключевых слов. В списке в [ключевые слова](../../cpp/keywords-cpp.md), ключевые слова, которые имеют два знака подчеркивания обычно представляют собой расширения Visual C++.  
  
## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Вне определения класса статических целочисленного const (или enum) члены  
 По стандарту (**/Za**), необходимо выполнить определение вне класса для элементов данных, как показано ниже:  
  
```  
  
      class CMyClass  {  
   static const int max = 5;  
   int m_array[max];  
}  
...  
const int CMyClass::max;   // out of class definition  
```  
  
 В разделе **/Ze**, определение вне класса является необязательным для членов данных статические, const целочисленные и константы перечисления. Только целых чисел и перечисления, static и const могут иметь инициализаторы в классе. Инициализация выражение должно быть выражение константы.  
  
 Чтобы избежать ошибок при определении вне класса предоставляется в заголовок файла и файл заголовков, включается в несколько исходных файлов, используйте [selectany](../../cpp/selectany.md). Пример:  
  
```  
__declspec(selectany) const int CMyClass::max = 5;  
```  
  
## <a name="casts"></a>Приведение типов  
 Компилятор C++ и компилятор C поддерживают эти виды приведения не удовлетворяющую стандарту ANSI.  
  
-   Приведение не соответствуют стандарту ANSI, для получения l значений. Пример:  
  
    ```  
    char *p;  
    (( int * ) p )++;  
    ```  
  
    > [!NOTE]
    >  Это расширение доступна только на языке C. Следующие стандартную форму ANSI C можно использовать в коде C++ для изменения указатель, как будто оно является указатель на другой тип.  
  
     Предыдущий пример можно переписать следующим образом для обеспечения соответствия стандарту ANSI C:.  
  
    ```  
    p = ( char * )(( int * )p + 1 );  
    ```  
  
-   Не соответствующие стандарту ANSI приведение указателя функции в указатель данных. Пример:  
  
    ```  
    int ( * pfunc ) ();   
    int *pdata;  
    pdata = ( int * ) pfunc;  
    ```  
  
     Чтобы выполнить такое же приведение, а также поддерживать ANSI-совместимости, можно привести указатель на функцию `uintptr_t` перед приведено в указатель данных:  
  
    ```  
    pdata = ( int * ) (uintptr_t) pfunc;  
    ```  
  
## <a name="variable-length-argument-lists"></a>Списки аргументов переменной длины  
 Компилятор C++ и компилятор C поддерживает декларатора функции, указывает переменное число аргументов, за которым следует определение функции, предоставляющей тип:  
  
```  
void myfunc( int x, ... );  
void myfunc( int x, char * c )  
{ }  
```  
  
## <a name="single-line-comments"></a>Однострочные комментарии  
 Компилятор C поддерживает однострочные комментарии, представленные с помощью двух косой черты (/ /) символами:  
  
```  
// This is a single-line comment.  
```  
  
## <a name="scope"></a>Область  
 Компилятор C поддерживает следующие функции, относящиеся к области.  
  
-   Переопределения extern статических элементов:  
  
    ```  
    extern int clip();  
    static int clip()  
    {}  
    ```  
  
-   Использование мягких переопределений typedef в той же области.  
  
    ```  
    typedef int INT;  
    typedef int INT;  
    ```  
  
-   Средства объявления функций имеют область видимости файла.  
  
    ```  
    void func1()  
    {  
        extern int func2( double );  
    }  
    int main( void )  
    {  
        func2( 4 );    //  /Ze passes 4 as type double  
    }                  //  /Za passes 4 as type int  
    ```  
  
-   Использование переменных области видимости блока, которые инициализируются с помощью неконстантного выражения:  
  
    ```  
    int clip( int );  
    int bar( int );  
    int main( void )  
    {  
        int array[2] = { clip( 2 ), bar( 4 ) };  
    }  
    int clip( int x )  
    {  
        return x;  
    }  
    int bar( int x )  
    {  
        return x;  
    }  
    ```  
  
## <a name="data-declarations-and-definitions"></a>Объявлениях и определениях данных  
 Компилятор C поддерживает следующие возможности объявления и определения данных.  
  
-   Смешанный символьные и строковые константы в инициализаторе:  
  
    ```  
    char arr[5] = {'a', 'b', "cde"};  
    ```  
  
-   Битовые поля, имеющих отличный от базовых типов **unsigned int** или **типа signed int**.  
  
-   Деклараторы, у которых нет типа.  
  
    ```  
    x;  
    int main( void )  
    {  
        x = 1;  
    }  
    ```  
  
-   Массивы без указанного размера в качестве последнего поля структуры или объединения:  
  
    ```  
    struct zero  
    {  
        char *c;  
        int zarray[];  
    };  
    ```  
  
-   Неименованные структуры (анонимным):  
  
    ```  
    struct  
    {  
        int i;  
        char *s;  
    };  
    ```  
  
-   Безымянные (анонимные) объединения:  
  
    ```  
    union  
    {  
        int i;  
        float fl;  
    };  
    ```  
  
-   Безымянные члены:  
  
    ```  
    struct s  
    {  
       unsigned int flag : 1;  
       unsigned int : 31;  
    }  
    ```  
  
## <a name="intrinsic-floating-point-functions"></a>Встроенные функции с плавающей запятой  
 Компилятор C++ и компилятор C поддерживает создание встроенных **x86 конкретных >** из `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, и `tan` функции **окончания x86 конкретных** при **/Oi** указано. Для компилятора c. совместимость со стандартом ANSI теряется при использовании этих встроенных функций, так как они не заданы `errno` переменной.  
  
## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Передача параметра неконстантного указателя в функцию ожидает ссылку на константный указатель  
 Это расширение языка C++. Этот код будет компилироваться с **/Ze**:  
  
```  
typedef   int   T;  
  
const T  acT = 9;      // A constant of type 'T'  
const T* pcT = &acT;   // A pointer to a constant of type 'T'  
  
void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'  
{  
   rpcT = pcT;  
}  
  
T*   pT;               // A pointer to a 'T'  
  
void func ()  
{  
   func2 ( pT );      // Should be an error, but isn't detected  
   *pT   = 7;         // Invalidly overwrites the constant 'acT'  
}  
```  
  
## <a name="iso646h-not-enabled"></a>ISO646. H не включено  
 В разделе **/Ze**, необходимо включить файл iso646.h, если вы хотите использовать текстовые формы следующих операторов:  
  
-   & & (и)  
  
-   & = (and_eq)  
  
-   & (bitand)  
  
-   &#124;(bitor)  
  
-   ~ (выполнить)  
  
-   ! (не)  
  
-   ! = (not_eq)  
  
-   &#124;&#124;(или)  
  
-   &#124;= (or_eq)  
  
-   ^ (xor)  
  
-   ^ = (xor_eq)  
  
## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Адрес строковый литерал имеет тип const char [], не const char (*)]  
 Приведенный ниже будет выводить char const (\*) [4] в группе **/Za**, но тип char const [4] в группе **/Ze**.  
  
```  
#include <stdio.h>  
#include <typeinfo>  
  
int main()  
{  
    printf_s("%s\n", typeid(&"abc").name());  
}  
```  
  
## <a name="see-also"></a>См. также  
 [/ Za, /Ze (отключить расширения языка)](../../build/reference/za-ze-disable-language-extensions.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)