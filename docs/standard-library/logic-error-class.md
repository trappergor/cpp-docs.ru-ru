---
title: "Класс logic_error | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdexcept/std::logic_error"
  - "std::logic_error"
  - "logic_error"
  - "std.logic_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logic_error - класс"
ms.assetid: b290d73d-94e1-4288-af86-2bb5d71f677a
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс logic_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс служит базовым для всех исключений, создаваемых для сообщения об ошибках, которые можно обнаружить до выполнения программы, таких как нарушение логических предварительных условий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class logic_error : public exception {  
public:  
    explicit logic_error(const string& message);

    explicit logic_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Заметки  
 Значение, возвращаемое [что](../standard-library/exception-class1.md) является копией **сообщение**`.`[данные](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Пример  
  
```  
// logic_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw logic_error( "logic error" );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
```  
  
 **Выходные данные**  
  
```  
Caught: logic error  
Type: class std::logic_error  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< stdexcept>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
[Класс Exception](../standard-library/exception-class1.md)  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

