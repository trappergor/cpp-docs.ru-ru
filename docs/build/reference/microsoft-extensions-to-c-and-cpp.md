---
title: Расширения Майкрософт для языков C и C++
ms.date: 06/14/2018
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
ms.openlocfilehash: dab8ac23be8b66ca84c57514c6c04e94dddebaae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321193"
---
# <a name="microsoft-extensions-to-c-and-c"></a>Расширения Майкрософт для языков C и C++

Visual C++ расширяет стандартом ANSI C и ANSI C++ следующим образом.

## <a name="keywords"></a>Ключевые слова

Добавляются несколько ключевых слов. В списке [ключевые слова](../../cpp/keywords-cpp.md), ключевые слова, которые имеют двумя символами подчеркивания в начале являются расширениями Visual C++.

## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Вне определения класса статических членов const целочисленный тип (или enum)

В стандарте (**/Za**), необходимо определение out-of класса для элементов данных, как показано ниже:

```cpp
class CMyClass  {
   static const int max = 5;
   int m_array[max];
}
// . . .
const int CMyClass::max;   // out of class definition
```

В разделе **/Ze**, определение вне класса не является обязательным для константных целочисленных и константных перечисляющих элементы данных. Только целых чисел и перечислений, static и const, могут иметь инициализаторы в классе; выражение инициализации должен быть const.

Чтобы избежать ошибок при определении вне класса предоставляется в заголовок файла и файл заголовка включен в несколько исходных файлов, используйте [selectany](../../cpp/selectany.md). Пример:

```cpp
__declspec(selectany) const int CMyClass::max = 5;
```

## <a name="casts"></a>Приведение типов

Компилятор C++ и компилятор C поддерживают такого рода приведения не удовлетворяющую стандарту ANSI.

- Приведение не соответствуют стандарту ANSI для получения l значений. Пример:

   ```C
   char *p;
   (( int * ) p )++;
   ```

   > [!NOTE]
   > Это расширение доступно только на языке C. Изменение указателя, если это указатель на другой тип можно использовать следующие стандартную форму ANSI C в коде C++.

   Предыдущий пример можно переписать следующим образом для обеспечения соответствия для стандарта ANSI C.

   ```C
   p = ( char * )(( int * )p + 1 );
   ```

- Не соответствуют стандарту ANSI приведение указателя функции в указатель на данные. Пример:

   ```C
   int ( * pfunc ) ();
   int *pdata;
   pdata = ( int * ) pfunc;
   ```

   Чтобы выполнить такое же приведение и также обеспечить совместимость с ANSI, можно привести указатель на функцию `uintptr_t` перед привести его к указателю данных:

   ```C
   pdata = ( int * ) (uintptr_t) pfunc;
   ```

## <a name="variable-length-argument-lists"></a>Списки аргументов переменной длины

Компилятор C++ и компилятор C поддерживают декларатор функции, указывает переменное число аргументов, за которым следует определение функции, предоставляющий тип вместо:

```cpp
void myfunc( int x, ... );
void myfunc( int x, char * c )
{ }
```

## <a name="single-line-comments"></a>Однострочные комментарии

Компилятор C поддерживает однострочные комментарии, которые были введены с помощью двух косой черты (/ /) символами:

```C
// This is a single-line comment.
```

## <a name="scope"></a>Область

Компилятор C поддерживает следующие функции, относящиеся к области.

- Переопределения extern элементов как static:

   ```C
   extern int clip();
   static int clip()
   {}
   ```

- Использование мягких переопределений typedef в той же области.

   ```C
   typedef int INT;
   typedef int INT;
   ```

- Средства объявления функций имеют область видимости файла:

   ```C
   void func1()
   {
       extern int func2( double );
   }
   int main( void )
   {
       func2( 4 );    //  /Ze passes 4 as type double
   }                  //  /Za passes 4 as type int
   ```

- Использование переменных области видимости блока, которые инициализируются с помощью неконстантного выражения:

   ```C
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

## <a name="data-declarations-and-definitions"></a>Объявлениям и определениям данных

Компилятор C поддерживает следующие возможности объявления и определения данных.

- Смешанный символьные и строковые константы в инициализаторе:

   ```C
   char arr[5] = {'a', 'b', "cde"};
   ```

- Битовые поля, которые имеют базовые типы, отличные от **unsigned int** или **целочисленное число со знаком**.

- Деклараторы, у которых нет типа.

   ```C
   x;
   int main( void )
   {
       x = 1;
   }
   ```

- Массивы без указанного размера, как последнее поле структур и объединений:

   ```C
   struct zero
   {
       char *c;
       int zarray[];
   };
   ```

- Неименованные структуры (анонимный):

   ```C
   struct
   {
       int i;
       char *s;
   };
   ```

- Неименованные (анонимные) объединения:

   ```C
   union
   {
       int i;
       float fl;
   };
   ```

- Безымянные члены:

   ```C
   struct s
   {
      unsigned int flag : 1;
      unsigned int : 31;
   }
   ```

## <a name="intrinsic-floating-point-functions"></a>Встроенные функции с плавающей запятой

Оба x86 компилятор C++ и компилятор C поддерживают создание встроенного `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, и `tan` функции при **/Oi** указан. Для компилятора C, соответствие ANSI теряется при использовании этих встроенных функций, так как они не устанавливайте `errno` переменной.

## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Передача параметра неконстантный указатель на функцию, ожидающий передачи ссылки на константный указатель

Это расширение языка C++. Этот код будет компилироваться с **/Ze**:

```cpp
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

В разделе **/Ze**, необходимо включить iso646.h, если вы хотите использовать текст вида следующие операторы:

- & & (и)

- &= (and_eq)

- & (bitand)

- &#124;(bitor)

- ~ (compl)

- ! (не)

- != (not_eq)

- &#124;&#124;(или)

- &#124;= (or_eq)

- ^ (xor)

- ^= (xor_eq)

## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Адрес строковый литерал имеет тип const char [], не const char (*)]

Следующий пример будет выводить `char const (*)[4]` под **/Za**, но `char const [4]` под **/Ze**.

```cpp
#include <stdio.h>
#include <typeinfo>

int main()
{
    printf_s("%s\n", typeid(&"abc").name());
}
```

## <a name="see-also"></a>См. также

- [/Za, /Ze (отключение расширений языка)](za-ze-disable-language-extensions.md)
- [Параметры компилятора MSVC](compiler-options.md)
- [Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
