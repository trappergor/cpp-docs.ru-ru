---
title: Псевдонимы и определения типов (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typedef_cpp
dev_langs:
- C++
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff0103a9debe63def6dbbcf7e3730a8e09dcbc2
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944454"
---
# <a name="aliases-and-typedefs-c"></a>Псевдонимы и определения типов (C++)
Можно использовать *объявления псевдонима* для объявления имени для использования в качестве синонима к ранее объявленному типу. (Этот механизм также называется неформально *псевдоним типа*). Этот механизм также можно использовать для создания *шаблон псевдонима*, который может быть особенно полезно для пользовательских механизмов выделения памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
using identifier = type;  
```  
  
## <a name="remarks"></a>Примечания  
 `identifier`  
 Имя псевдонима.  
  
 `type`  
 Идентификатор типа, для которого создается псевдоним.  
  
 Псевдоним не вводит в программу новый тип и не может менять значение существующего имени типа.  
  
 Самая простая форма псевдоним эквивалентно **typedef** механизм из C ++ 03:  
  
```cpp  
// C++11  
using counter = long;  
  
// C++03 equivalent:  
// typedef long counter;  
```  
  
 Оба этих механизма позволяют создавать переменные типа "счетчик". Псевдоним типа для `std::ios_base::fmtflags`, приведенный в следующем примере, может быть более полезен.  
  
```cpp  
// C++11  
using fmtfl = std::ios_base::fmtflags;  
  
// C++03 equivalent:  
// typedef std::ios_base::fmtflags fmtfl;  
  
fmtfl fl_orig = std::cout.flags();  
fmtfl fl_hex = (fl_orig & ~std::cout.basefield) | std::cout.showbase | std::cout.hex;  
// ...  
std::cout.flags(fl_hex);  
```  
  
 Псевдонимы также работают с указатели на функции, но гораздо более удобочитаемыми, чем эквивалентное определение типа:  
  
```cpp  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 Ограничение **typedef** механизмом является то, что он не работает с шаблонами. Напротив, синтаксис псевдонима типа в C ++11 позволяет создавать шаблоны псевдонимов:  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать шаблон псевдонима с пользовательским механизмом выделения памяти — в данном случае целочисленным векторным типом. Можно заменить любой тип для **int** создать удобный псевдоним для скрытия сложного параметра, перечислены в основном коде функций. Применяя по всему коду пользовательские механизмы выделения памяти, можно повысить удобочитаемость и уменьшить риск возникновения ошибок, связанных с опечатками.  
  
```cpp  
#include <stdlib.h>  
#include <new>  
  
template <typename T> struct MyAlloc {  
    typedef T value_type;  
  
    MyAlloc() { }  
    template <typename U> MyAlloc(const MyAlloc<U>&) { }  
  
    bool operator==(const MyAlloc&) const { return true; }  
    bool operator!=(const MyAlloc&) const { return false; }  
  
    T * allocate(const size_t n) const {  
        if (n == 0) {  
            return nullptr;  
        }  
  
        if (n > static_cast<size_t>(-1) / sizeof(T)) {  
            throw std::bad_array_new_length();  
        }  
  
        void * const pv = malloc(n * sizeof(T));  
  
        if (!pv) {  
            throw std::bad_alloc();  
        }  
  
        return static_cast<T *>(pv);  
    }  
  
    void deallocate(T * const p, size_t) const {  
        free(p);  
    }  
};  
  
#include <vector>  
using MyIntVector = std::vector<int, MyAlloc<int>>;  
  
#include <iostream>  
  
int main ()   
{  
    MyIntVector foov = { 1701, 1764, 1664 };  
  
    for (auto a: foov) std::cout << a << " ";  
    std::cout << "\n";  
  
    return 0;  
}  
```  
  
```Output  
1701 1764 1664  
```  
  
## <a name="typedefs"></a>Определения типов  
 Объект **typedef** объявление вводит имя, которое в своей области действия становится синонимом типа, заданного параметром *объявление_типа* часть объявления.  
  
 Объявления typedef можно использовать для создания более коротких или более понятных имен для типов, уже определенных в языке или объявленных пользователем. Имена typedef позволяют инкапсулировать детали реализации, которые могут измениться.  
  
 Отличается от **класс**, **структуры**, **объединение**, и **перечисления** объявления, **typedef** объявления не добавляют новые типы — они вводят новые имена для существующих типов.  
  
 Имена, объявленные с **typedef** занимают то же пространство имен, что и другие идентификаторы (за исключением меток операторов). Таким образом, в них не может использоваться тот же идентификатор, что и в объявленном ранее имени, за исключением случаев, когда они находятся в объявлении типа класса. Рассмотрим следующий пример.  
  
```cpp 
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 Правила скрытия имен, которые относятся к другим идентификаторам, управляют и видимостью имен, объявленные с помощью **typedef**. Поэтому следующий код допустим в C++:  
  
```cpp 
// typedef_names2.cpp  
typedef unsigned long UL;   // Declare a typedef name, UL  
int main()  
{  
   unsigned int UL;   // Redeclaration hides typedef name  
}  
  
// typedef UL back in scope  
```  
 
  
```cpp 
// typedef_specifier1.cpp  
typedef char FlagType;  
  
int main()  
{  
}  
  
void myproc( int )  
{  
    int FlagType;  
}  
```  
  
 При объявлении в локальной области идентификатора с тем же именем, что и имя typedef, или при объявлении члена структуры либо объединения в той же области или во внутренней области обязательно должен указываться спецификатор типа. Пример:  
  
```cpp 
typedef char FlagType;  
const FlagType x;  
```  
  
 Чтобы повторно использовать имя `FlagType` для идентификатора, члена структуры или члена объединения, необходимо указать тип:  
  
```cpp 
const int FlagType;  // Type specifier required  
```  
  
 Недостаточно написать  
  
```cpp 
const FlagType;      // Incomplete specification  
```  
  
 поскольку `FlagType` воспринимается как часть типа, а не как заново объявляемый идентификатор. Это объявление недопустимо, как и  
  
```cpp 
int;  // Illegal declaration   
```  
  
 С помощью typedef можно объявить любой тип, включая типы указателей, функций и массивов. Имя typedef для типа указателя на структуру или объединение можно объявить до определения типа структуры или объединения, если только определение находится в той же области видимости, что и объявление.  
  
### <a name="examples"></a>Примеры  
 Один из способов использования **typedef** объявления — чтобы сделать объявления более унифицированными и компактными. Пример:  
  
```cpp  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 Чтобы использовать **typedef** указать основные и производные типы в одном объявлении, деклараторы можно разделить запятыми. Пример:  
  
```cpp 
typedef char CHAR, *PSTR;  
```  
  
 В следующем примере задан тип `DRAWF` для функции, не возвращающей никакого значения и принимающей два аргумента int.  
  
```cpp 
typedef void DRAWF( int, int );  
```  
  
 После выполнения приведенного выше **typedef** инструкции, объявления  
  
```cpp 
DRAWF box;   
```  
  
 будет эквивалентно следующему:  
  
```cpp 
void box( int, int );  
```  
  
 **TypeDef** сочетается с **структуры** позволяют объявлять и именовать пользовательские типы:  
  
```cpp  
// typedef_specifier2.cpp  
#include <stdio.h>  
  
typedef struct mystructtag  
{  
    int   i;  
    double f;  
} mystruct;  
  
int main()  
{  
    mystruct ms;  
    ms.i = 10;  
    ms.f = 0.99;  
    printf_s("%d   %f\n", ms.i, ms.f);  
}  
``` 
  
```Output  
10   0.990000  
``` 
  
### <a name="re-declaration-of-typedefs"></a>Повторное объявление определений типов  
 **Typedef** объявление может использоваться для повторного объявления же имени для ссылки на тот же тип. Пример:  
  
```cpp  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
``` 
  
 Программа *PROG. CPP* включает два файла заголовков, которые содержат **typedef** объявления для имени `CHAR`. Если в обеих объявлениях указывается один и тот же тип, такое повторное объявление допустимо.  
  
 Объект **typedef** не может переопределить имя, которое было объявлено с другим типом. Таким образом Если *"файл2". H* содержит  
  
```cpp  
// FILE2.H  
typedef int CHAR;     // Error  
``` 
  
 компилятор выдает ошибку из-за попытки повторного объявления имени `CHAR` как имени другого типа. Это правило распространяется также на конструкции, подобные следующим:  
  
```cpp  
typedef char CHAR;  
typedef CHAR CHAR;      // OK: redeclared as same type  
  
typedef union REGS      // OK: name REGS redeclared  
{                       //  by typedef name with the  
    struct wordregs x;  //  same meaning.  
    struct byteregs h;  
} REGS;  
``` 
  
### <a name="typedefs-in-c-vs-c"></a>определения типов в C++ и В  
 Использование **typedef** поддерживается описатель с типами классов, главным образом из-за ANSI C возможности объявлять неименованные структуры в **typedef** объявления. Например, многие программисты C используют следующий код.  
  
```cpp  
// typedef_with_class_types1.cpp  
// compile with: /c  
typedef struct {   // Declare an unnamed structure and give it the  
                   // typedef name POINT.  
   unsigned x;  
   unsigned y;  
} POINT;  
``` 
  
 Преимущество такого объявления заключает в том, что можно выполнять объявления  
  
```cpp  
POINT ptOrigin;  
``` 
  
 вместо  
  
```cpp 
struct point_t ptOrigin;  
```  
  
 В C++ различие между **typedef** имена и реальными типами (объявлен с **класс**, **структуры**, **объединение**и **перечисления** ключевые слова) более четкое. Хотя практика объявлять безымянные структуры в C **typedef** инструкции по-прежнему работает, он обеспечивает никаких значимых преимуществ, как на языке C.  
  
```cpp  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 В предыдущем примере объявляется класс с именем `POINT` с помощью неименованного класса **typedef** синтаксис. `POINT` считается именем класса, однако к именам, предоставленным таким образом, применяются следующие ограничения.  
  
-   Имя (синоним) не может следовать за **класс**, **структуры**, или **объединение** префикс.  
  
-   Имя не может использоваться в качестве имени конструктора или деструктора в объявлении класса.  
  
 Таким образом, этот синтаксис не предоставляет механизм наследования, создания или удаления.  
