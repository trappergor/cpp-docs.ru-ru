---
title: "const (C++) | Microsoft Docs"
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
  - "const_cpp"
  - "const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const - ключевое слово [C++]"
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# const (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При изменении объявления данных ключевое слово **const** указывает, что объект или переменная не могут изменяться.  
  
## Синтаксис  
  
```  
  
        const declaration ;  
member-function const ;  
```  
  
## Значения\-константы  
 Ключевое слово **const** указывает, что значение переменной является постоянным и сообщает компилятору, что программист не должен его изменять.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 В языке C\+\+ ключевое слово **const** можно использовать вместо директивы препроцессора [\#define](../preprocessor/hash-define-directive-c-cpp.md) для определения значения констант.  Значения, определенные с ключевым словом **const**, проходят проверку типа и могут использоваться вместо константных выражений.  В языке C\+\+ можно задать размер массива с помощью переменной **const**, как показано ниже:  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 В языке C константные значения по умолчанию имеют внешнюю компоновку, поэтому они могут использоваться только в файлах исходного кода.  В языке C\+\+ константные значения по умолчанию имеют внутреннюю компоновку, которая позволяет использовать их в файлах заголовков.  
  
 Ключевое слово **const** также можно использовать в объявлениях указателей.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Указатель на переменную, объявленную как **const**, может быть присвоен только указателю, который также объявлен как **const**.  
  
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
  
 Указатели на данные\-константы можно использовать в качестве параметров функций, чтобы функция не могла изменять параметр, переданный посредством указателя.  
  
 Для объектов, которые объявлены как **const**, можно вызывать только [константные функции\-члены](../misc/constant-member-functions.md).  Это гарантирует, что константный объект не будет изменен.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Для объектов, не объявленных как константы, можно вызывать как константные, так и неконстантные функции\-члены.  Можно также перегрузить функцию\-член с использованием ключевого слова **const**; это позволяет вызывать разные версии функции для константных и неконстантных объектов.  
  
 Не допускается объявление конструкторов и деструкторов с ключевым словом **const**.  
  
## Функции\-члены\-константы  
 Объявление функции\-члена с ключевым словом **const** указывает, что функция доступна только для чтения и не изменяет объект, для которого вызывается.  Функция\-член\-константа не может изменить никакие нестатические элементы данных или вызвать какую\-либо функцию\-член, не являющуюся константой. Чтобы объявить функцию\-член\-константу, поместите ключевое слово **const** после закрывающей скобки списка аргументов.  Ключевое слово **const** необходимо указать как в объявлении, так и в определении.  
  
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
  
## Различия констант в языках C и C\+\+  
 При объявлении переменной как **const** в файле исходного кода на языке C это делается следующим образом:  
  
```  
const int i = 2;  
```  
  
 Затем эту переменную можно использовать в другом модуле следующим образом:  
  
```  
extern const int i;  
```  
  
 Однако в языке C\+\+ для обеспечения аналогичного поведения необходимо объявить переменную **const** следующим образом:  
  
```  
extern const int i = 2;  
```  
  
 Если требуется объявить переменную `extern` в файле исходного кода C\+\+ для использования в файле исходного кода C, следует использовать:  
  
```  
extern "C" const int x=10;  
```  
  
 для предотвращения изменения имени компилятором C\+\+.  
  
## Заметки  
 Если ключевое слово **const** используется после списка параметров функции\-члена, это означает, что такая функция не меняет объект, для которого она была вызвана.  
  
 Дополнительные сведения о ключевом слове см. **const** см. в следующих разделах:  
  
-   [Значения констант](../misc/constant-values.md)  
  
-   [Константные функции\-члены](../misc/constant-member-functions.md)  
  
-   [Указатели с ключевыми словами const и volatile](../Topic/const%20and%20volatile%20Pointers.md)  
  
-   [Квалификаторы типов \(Справочник по языку C\)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [\#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)