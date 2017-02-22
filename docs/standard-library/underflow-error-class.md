---
title: "Класс underflow_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdexcept/std::underflow_error"
  - "underflow_error"
  - "std.underflow_error"
  - "std::underflow_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underflow_error - класс"
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс underflow_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс служит базовым для всех исключений, создаваемых для сообщения об арифметической неточности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class underflow_error : public runtime_error {  
public:  
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Заметки  
 Значение, возвращаемое [что](../standard-library/exception-class1.md) является копией **сообщение**`.`[данные](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Пример  
  
```  
// underflow_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw underflow_error( "The number's a bit small, captain!" );  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught: The number's a bit small, captain!  
Type: class std::underflow_error  
*\  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< stdexcept>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\< stdexcept> члены](http://msdn.microsoft.com/ru-ru/7b6b0a73-916e-44aa-9a3f-f5b6b3ce98e6)   
 [Класс runtime_error](../Topic/runtime_error%20Class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

