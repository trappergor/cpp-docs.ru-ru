---
title: "Имена без компоновки | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "перечислители [C++], компоновка"
  - "параметры функции [C++]"
  - "функции [C++], параметры"
  - "имена [C++], без компоновки"
  - "typedef - имена, компоновка"
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Имена без компоновки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Единственными именами без компоновки являются следующие:  
  
-   параметры функций.  
  
-   Имена с областью видимости "блок" не объявляются как `extern` или **статические**.  
  
-   Перечислители.  
  
-   Имена, объявленные в операторе `typedef`.  Исключение создается, если оператор `typedef` используется для предоставления имени для неименованного типа класса.  Имя может затем иметь внешнюю компоновку, если класс имеет внешнюю компоновку.  В следующем примере показана ситуация, в которой имя `typedef` имеет внешнюю компоновку.  
  
    ```  
    // names_with_no_linkage.cpp  
    typedef struct  
    {  
       short x;  
       short y;  
    } POINT;  
  
    extern int MoveTo( POINT pt );  
  
    int main()  
    {  
    }  
    ```  
  
     Имя `typedef`, `POINT`, становится именем класса для безымянной структуры.  Оно затем используется для объявления функции с внешней компоновкой.  
  
 Поскольку имена `typedef` не имеют никакой компоновки, их определения могут различаться в разных записях преобразования.  Поскольку компиляции выполняются непосредственно, не существует способа обнаружения этих различий компилятором.  В результате ошибки такого рода не обнаруживаются до компоновки.  Рассмотрим следующий случай.  
  
```  
// Translation unit 1  
typedef int INT  
  
INT myInt;  
...  
  
// Translation unit 2  
typedef short INT  
  
extern INT myInt;  
...  
```  
  
 Предыдущий код вызывает ошибку "неразрешенного внешнего элемента" во время компоновки.  
  
## Пример  
 Функции C\+\+ могут быть определены только в области видимости файла или класса.  В следующем примере показано, как определять функции, и продемонстрировано ошибочное определение функции.  
  
```  
// function_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void ShowChar( char ch );    // Declare function ShowChar.  
  
void ShowChar( char ch )     // Define function ShowChar.  
{                            // Function has file scope.  
   cout << ch;  
}  
  
struct Char                  // Define class Char.  
{  
    char Show();             // Declare Show function.  
    char Get();              // Declare Get function.  
    char ch;  
};  
  
char Char::Show()            // Define Show function  
{                            //  with class scope.  
    cout << ch;  
    return ch;  
}  
  
void GoodFuncDef( char ch )  // Define GoodFuncDef  
{                            //  with file scope.  
    int BadFuncDef( int i )  // C2601, Erroneous attempt to  
    {                        //  nest functions.  
        return i * 7;  
    }  
    for( int i = 0; i < BadFuncDef( 2 ); ++i )  
        cout << ch;  
    cout << "\n";  
}  
```  
  
## См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)