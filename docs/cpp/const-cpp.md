---
title: "const (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: const_cpp
dev_langs: C++
helpviewer_keywords: const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8290b9c73dbab2c3cc3ab63cfbff10f587e46d7b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="const-c"></a>const (C++)
При изменении объявления данных **const** ключевое слово указывает, что объект или переменная не является изменяемым.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      const declaration ;  
member-function const ;  
```  
  
## <a name="const-values"></a>Значения-константы  
 **Const** ключевое слово указывает, что значение переменной является постоянным и указывает компилятору, что программист не должен его изменять.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 В C++ можно использовать **const** ключевое слово, а не [#define](../preprocessor/hash-define-directive-c-cpp.md) директивы препроцессора для определения значения констант. Значения, определенные с **const** , проходят проверку типа и может использоваться вместо константных выражений. В C++ можно указать размер массива с **const** переменной следующим образом:  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 В языке C константные значения по умолчанию имеют внешнюю компоновку, поэтому они могут использоваться только в файлах исходного кода. В языке C++ константные значения по умолчанию имеют внутреннюю компоновку, которая позволяет использовать их в файлах заголовков.  
  
 **Const** ключевое слово может также использоваться в объявлениях указателей.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Переменная, объявленная как указатель **const** могут быть назначены только указатель, который также объявляется как **const**.  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 Указатели на данные-константы можно использовать в качестве параметров функций, чтобы функция не могла изменять параметр, переданный посредством указателя.  
  
 Для объектов, которые объявляются как **const**, можно вызывать только член-константу функции. Это гарантирует, что константный объект не будет изменен.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Для объектов, не объявленных как константы, можно вызывать как константные, так и неконстантные функции-члены. Можно также перегрузить функции члена с помощью **const** ключевого слова; это позволяет вызывать разные версии функции для константных и неконстантных объектов.  
  
 Нельзя объявлять конструкторов и деструкторов с **const** ключевое слово.  
  
## <a name="const-member-functions"></a>Функции-члены-константы  
 Объявление функции-члена с **const** ключевое слово указывает, что функция «только для чтения» функцию, которая не изменяет объект, для которого он вызван. Функции-члена константы не может изменить никакие нестатические данные элементы или вызова функций, которые не являются константой любого члена. Чтобы объявить функцию-член-константу, поместите **const** ключевое слово после закрывающей скобки списка аргументов. **Const** ключевое слово является обязательным в объявлении и определении.  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## <a name="c-and-c-const-differences"></a>Различия констант в языках C и C++  
 При объявлении переменной как **const** в файл исходного кода C это делается следующим образом:  
  
```  
const int i = 2;  
```  
  
 Затем эту переменную можно использовать в другом модуле следующим образом:  
  
```  
extern const int i;  
```  
  
 Однако для обеспечения аналогичного поведения в C++, необходимо объявить вашей **const** переменной как:  
  
```  
extern const int i = 2;  
```  
  
 Если требуется объявить переменную `extern` в файле исходного кода C++ для использования в файле исходного кода C, следует использовать:  
  
```  
extern "C" const int x=10;  
```  
  
 для предотвращения изменения имени компилятором C++.  
  
## <a name="remarks"></a>Примечания  
 Если после списка параметров функции-члена, **const** ключевое слово указывает, что функция не изменяет объект, для которого он вызывается.  
  
 Дополнительные сведения о **const**, см. в следующих разделах:  
    
-   [Указатели с ключевыми словами const и volatile](../cpp/const-and-volatile-pointers.md)  
  
-   [Квалификаторы типов (Справочник по языку C)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)