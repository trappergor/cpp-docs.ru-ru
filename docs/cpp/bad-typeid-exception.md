---
title: "Исключение bad_typeid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bad_typeid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_typeid - исключение"
  - "исключения, bad_typeid"
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Исключение bad_typeid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Исключение `bad_typeid` вызывается [оператором typeid](../cpp/typeid-operator.md), если операнд для `typeid` является пустым \(NULL\) указателем.  
  
## Синтаксис  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## Заметки  
 Исключение `bad_typeid` имеет следующий интерфейс:  
  
```  
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 В следующем примере показан оператор `typeid`, вызывающий исключение `bad_typeid`.  
  
```  
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## Вывод  
  
```  
Object is NULL  
```  
  
## См. также  
 [Сведения о типах времени выполнения](../Topic/Run-Time%20Type%20Information.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)