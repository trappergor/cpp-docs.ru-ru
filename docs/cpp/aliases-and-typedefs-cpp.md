---
title: "Псевдонимы и определения типов (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "typedef"
dev_langs: 
  - "C++"
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Псевдонимы и определения типов (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью *объявления псевдонима* можно объявлять имя, которое будет использоваться в качестве синонима к ранее объявленному типу.  \(В обычной речи такой механизм также называют *псевдонимом типа*.\)  С помощью этого механизма также можно создать *шаблон псевдонима*, который может быть особенно полезен для пользовательских механизмов выделения памяти.  
  
## Синтаксис  
  
```  
  
using identifier = type;  
```  
  
## Заметки  
 `identifier`  
 Имя псевдонима.  
  
 `type`  
 Идентификатор типа, для которого создается псевдоним.  
  
 Псевдоним не вводит в программу новый тип и не может менять значение существующего имени типа.  
  
 В простейшей форме псевдонимы эквивалентны механизму `typedef` из версии языка C\+\+03:  
  
```cpp  
  
// C++11  
using counter = long;  
  
// C++03 equivalent:  
// typedef long counter;  
  
```  
  
 Оба этих механизма позволяют создавать переменные типа "счетчик".  Псевдоним типа для `std::ios_base::fmtflags`, приведенный в следующем примере, может быть более полезен.  
  
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
  
 Псевдонимы также работают с указателями на функции, однако они обеспечивают большую удобочитаемость, чем их эквивалент typedef.  
  
```cpp  
  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 Механизм `typedef` имеет ограничение: он не работает с шаблонами.  Напротив, синтаксис псевдонима типа в C \+\+11 позволяет создавать шаблоны псевдонимов:  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## Пример  
 В следующем примере показано, как использовать шаблон псевдонима с пользовательским механизмом выделения памяти — в данном случае целочисленным векторным типом.  Любой тип можно заменить на `int`, чтобы создать удобный псевдоним для скрытия сложных списков параметров в основном коде функций.  Применяя по всему коду пользовательские механизмы выделения памяти, можно повысить удобочитаемость и уменьшить риск возникновения ошибок, связанных с опечатками.  
  
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
  
## Вывод  
  **1701 1764 1664**   
## Typedefs  
 Объявление `typedef` вводит в программу имя, которое в своей области видимости становится синонимом для типа, заданного параметром *объявление\-типа* в этом объявлении.  
  
 Объявления typedef можно использовать для создания более коротких или более понятных имен для типов, уже определенных в языке или объявленных пользователем.  Имена typedef позволяют инкапсулировать детали реализации, которые могут измениться.  
  
 В отличие от объявлений **class**, `struct`, **union** и `enum`, объявления `typedef` вводят в программу не новые типы, а новые имена для уже существующих типов.  
  
 Имена, объявленные с ключевым словом `typedef`, занимают то же пространство имен, что и другие идентификаторы \(за исключением меток операторов\).  Таким образом, в них не может использоваться тот же идентификатор, что и в объявленном ранее имени, за исключением случаев, когда они находятся в объявлении типа класса.  Рассмотрим следующий пример.  
  
```  
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 Правила скрытия имен, которые относятся к другим идентификаторам, управляют и видимостью имен, объявленных с ключевым словом `typedef`.  Поэтому следующий код допустим в C\+\+:  
  
```  
// typedef_names2.cpp  
typedef unsigned long UL;   // Declare a typedef name, UL  
int main()  
{  
   unsigned int UL;   // Redeclaration hides typedef name  
}  
  
// typedef UL back in scope  
```  
  
-   [Повторное объявление имен typedef](../misc/redeclaration-of-typedef-names.md)  
  
-   [Использование typedef с типами классов](../misc/use-of-typedef-with-class-types.md)  
  
-   [Пространство имен для имен typedef](../misc/name-space-of-typedef-names.md)  
  
```  
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
  
 При объявлении в локальной области идентификатора с тем же именем, что и имя typedef, или при объявлении члена структуры либо объединения в той же области или во внутренней области обязательно должен указываться спецификатор типа.  Пример:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Чтобы повторно использовать имя `FlagType` для идентификатора, члена структуры или члена объединения, необходимо указать тип:  
  
```  
const int FlagType;  // Type specifier required  
```  
  
 Недостаточно написать  
  
```  
const FlagType;      // Incomplete specification  
```  
  
 поскольку `FlagType` воспринимается как часть типа, а не как заново объявляемый идентификатор.  Это объявление недопустимо, как и  
  
```  
int;  // Illegal declaration   
```  
  
 С помощью typedef можно объявить любой тип, включая типы указателей, функций и массивов.  Имя typedef для типа указателя на структуру или объединение можно объявить до определения типа структуры или объединения, если только определение находится в той же области видимости, что и объявление.  
  
### Примеры  
 Одна из причин, по которым используются объявления `typedef`, заключается в том, чтобы сделать объявления более унифицированными и компактными.  Пример:  
  
```  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 Для того чтобы при помощи ключевого слова `typedef` определить основные и производные типы в одном и том же объявлении, деклараторы можно разделять запятыми.  Пример:  
  
```  
typedef char CHAR, *PSTR;  
```  
  
 В следующем примере задан тип `DRAWF` для функции, не возвращающей никакого значения и принимающей два аргумента int.  
  
```  
typedef void DRAWF( int, int );  
```  
  
 После выполнения приведенного выше оператора `typedef` следующее объявление:  
  
```  
DRAWF box;   
```  
  
 будет эквивалентно следующему:  
  
```  
void box( int, int );  
```  
  
 Ключевые слова `typedef` и `struct` часто объединяются, что позволяют объявлять и именовать пользовательские типы:  
  
```  
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
  
  **10   0.990000**   
### Повторное объявление определений типов  
 Объявление `typedef` можно использовать для повторного объявления того же имени с указанием того же типа.  Пример:  
  
```  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
```  
  
 Программа PROG.CPP содержит два файла заголовков, в каждом из которых имеются объявления `typedef` имени `CHAR`.  Если в обеих объявлениях указывается один и тот же тип, такое повторное объявление допустимо.  
  
 `typedef` не может переопределить имя, которое было объявлено как имя другого типа.  Поэтому, если файл FILE2.H содержит  
  
```  
// FILE2.H  
typedef int CHAR;     // Error  
```  
  
 компилятор выдает ошибку из\-за попытки повторного объявления имени `CHAR` как имени другого типа.  Это правило распространяется также на конструкции, подобные следующим:  
  
```  
typedef char CHAR;  
typedef CHAR CHAR;      // OK: redeclared as same type  
  
typedef union REGS      // OK: name REGS redeclared  
{                       //  by typedef name with the  
    struct wordregs x;  //  same meaning.  
    struct byteregs h;  
} REGS;  
```  
  
### определения типов в C\+\+ иC  
 Использование описателя `typedef` с типами класса имеет широкую поддержку благодаря возможности объявлять неименованные структуры в объявлениях `typedef`, предоставляемой стандартом ANSI C.  Например, многие программисты C используют следующий код.  
  
```  
// typedef_with_class_types1.cpp  
// compile with: /c  
typedef struct {   // Declare an unnamed structure and give it the  
                   // typedef name POINT.  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 Преимущество такого объявления заключает в том, что можно выполнять объявления  
  
```  
POINT ptOrigin;  
```  
  
 вместо  
  
```  
struct point_t ptOrigin;  
```  
  
 В C\+\+ различие между именами `typedef` и реальными типами \(объявленными с ключевыми словами **class**, `struct`, **union** и `enum`\) более четкое.  Хотя предоставляемая в С возможность объявлять безымянные структуры в операторе `typedef` по\-прежнему работает, она не предоставляет никаких значимых преимуществ, как в C.  
  
```  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 В предыдущем примере класс `POINT` объявляется с помощью синтаксиса `typedef` неименованного класса.  `POINT` считается именем класса, однако к именам, предоставленным таким образом, применяются следующие ограничения.  
  
-   Имя \(синоним\) не может находиться после префикса **class**, `struct` или **union**.  
  
-   Имя не может использоваться в качестве имени конструктора или деструктора в объявлении класса.  
  
 Таким образом, этот синтаксис не предоставляет механизм наследования, создания или удаления.  
  
## См. также  
 [Ключевое слово using](../misc/using-keyword.md)