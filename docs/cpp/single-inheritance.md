---
title: Одиночное наследование | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- single inheritance
- base classes [C++], indirect
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- derived classes [C++], single base class
- inheritance, single
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b06bceadf9a274253693dc8f33f3d04e6500115
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028624"
---
# <a name="single-inheritance"></a>Одиночное наследование
При единичном наследовании, самой распространенной форме наследования, каждый класс имеет только один базовый класс. Рассмотрим пример взаимоотношений на следующем рисунке.  
  
 ![Основные одним&#45;граф наследования](../cpp/media/vc38xj1.gif "vc38XJ1")  
Граф простого одиночного наследования  
  
 Обратите внимание на переход от общего к конкретному на этом рисунке. В структуре большинства иерархий классов заметна еще одна общая особенность: каждый производный класс является разновидностью базового класса. На этом рисунке видно, что класс `Book` является разновидностью класса `PrintedDocument`, а `PaperbackBook` — разновидностью класса `book`.  
  
 На этом рисунке необходимо обратить внимание еще на одну особенность: `Book` является не только производным (от класса `PrintedDocument`), но и базовым классом (`PaperbackBook` является производным от `Book`). В следующем примере показана структура объявления такой иерархии классов:  
  
```cpp 
// deriv_SingleInheritance.cpp  
// compile with: /LD  
class PrintedDocument {};  
  
// Book is derived from PrintedDocument.  
class Book : public PrintedDocument {};  
  
// PaperbackBook is derived from Book.  
class PaperbackBook : public Book {};  
```  
  
 Для `PrintedDocument` класс `Book` считается прямым базовым классом, а для `PaperbackBook` — косвенным. Различие заключается в том, что первый из них выводится в списке базовых классов в объявлении класса, а последний — нет.  
  
 Базовый класс, производными от которого являются другие классы, объявляется раньше производных классов. Для базового класса недостаточно предоставить объявление с опережающей ссылкой; объявление должно быть полным.  
  
 В приведенном выше примере спецификатор доступа **открытый** используется. Значение public, protected и закрытого наследования описан в [управления доступом к членам.](../cpp/member-access-control-cpp.md)  
  
 Один класс может быть базовым для нескольких более специализированных классов, как показано в следующем примере.  
  
 ![Направленный ациклический граф](../cpp/media/vc38xj2.gif "vc38XJ2")  
Пример ориентированного ациклического графа  
  
 На приведенной выше схеме ориентированного ациклического графа (DAG) некоторые классы являются базовыми для нескольких производных классов. Но обратное не выполняется: для каждого производного класса имеется только один прямой базовый класс. На этом рисунке представлена структура с единичным наследованием.  
  
> [!NOTE]
>  Ориентированные ациклические графы могут описывать структуры не только с единичным, но и с множественным наследованием. В этом разделе рассматривается в [множественное наследование](http://msdn.microsoft.com/3b74185e-2beb-4e29-8684-441e51d2a2ca).  
  
 При наследовании производный класс содержит члены базового класса, а также те члены, которые вы в него добавили. В результате производный класс может обращаться к членам базового класса (если в производном классе такие члены были переопределены). Если члены прямых или косвенных базовых классов были переопределены в производном классе, то обращаться к ним можно при помощи оператора разрешения области видимости (`::`). Рассмотрим следующий пример.  
  
```cpp 
// deriv_SingleInheritance2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
class Document {  
public:  
   char *Name;   // Document name.  
   void PrintNameOf();   // Print name.  
};  
  
// Implementation of PrintNameOf function from class Document.  
void Document::PrintNameOf() {  
   cout << Name << endl;  
}  
  
class Book : public Document {  
public:  
   Book( char *name, long pagecount );  
private:  
   long  PageCount;  
};  
  
// Constructor from class Book.  
Book::Book( char *name, long pagecount ) {  
   Name = new char[ strlen( name ) + 1 ];  
   strcpy_s( Name, strlen(Name), name );  
   PageCount = pagecount;  
};  
```  
  
 Обратите внимание, что конструктор класса `Book` (`Book::Book`) может обращаться к элементу данных `Name`. В программе объект типа `Book` можно создать и использовать следующим образом:  
  
```cpp 
//  Create a new object of type Book. This invokes the  
//   constructor Book::Book.  
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );  
  
...  
  
//  Use PrintNameOf function inherited from class Document.  
LibraryBook.PrintNameOf();  
```  
  
 Как показано в предыдущем примере, член класса и наследуемые данные и функции используются одинаково. Если реализации класса `Book` требует повторно реализовать функцию `PrintNameOf`, то та функция, которая принадлежит классу `Document`, может вызываться только при помощи оператора разрешения области видимости (`::`):  
  
```cpp 
// deriv_SingleInheritance3.cpp  
// compile with: /EHsc /LD  
#include <iostream>  
using namespace std;  
  
class Document {  
public:  
   char *Name;          // Document name.  
   void  PrintNameOf() {}  // Print name.  
};  
  
class Book : public Document {  
   Book( char *name, long pagecount );  
   void PrintNameOf();  
   long  PageCount;  
};  
  
void Book::PrintNameOf() {  
   cout << "Name of book: ";  
   Document::PrintNameOf();  
}  
```  
  
 Указатели и ссылки на производные классы могут быть неявно преобразованы в указатели и ссылки на их базовые классы (если имеется доступный и однозначный базовый класс). Эта концепция показана в следующем фрагменте кода на примере указателей (тот же принцип действует и для ссылок):  
  
```cpp 
// deriv_SingleInheritance4.cpp  
// compile with: /W3  
struct Document {  
   char *Name;  
   void PrintNameOf() {}  
};  
  
class PaperbackBook : public Document {};  
  
int main() {  
   Document * DocLib[10];   // Library of ten documents.  
   for (int i = 0 ; i < 5 ; i++)  
      DocLib[i] = new Document;  
   for (int i = 5 ; i < 10 ; i++)  
      DocLib[i] = new PaperbackBook;  
}  
```  
  
 В приведенном выше примере создаются разные типы. Однако поскольку все эти типы являются производными от класса `Document`, то выполняется неявное преобразование в `Document *`. В результате этого массив `DocLib` содержит объекты разных типов и является "разнородным списком" (то есть не все его объекты относятся к одному и тому же типу).  
  
 Поскольку класс `Document` имеет функцию `PrintNameOf`, он позволяет напечатать имя каждой книги в библиотеке, хотя при этом может опускаться часть информации, которая характерна только для данного типа документов (количество страниц для класса `Book`, размер в байтах для класса `HelpFile` и т. д).  
  
> [!NOTE]
>  Такие функции, как `PrintNameOf`, не рекомендуется реализовывать в базовых классах. [Виртуальные функции](../cpp/virtual-functions.md) эффективным.  
  
