---
title: "Класс out_of_range | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "out_of_range"
  - "stdexcept/std::out_of_range"
  - "std.out_of_range"
  - "std::out_of_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out_of_range - класс"
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# Класс out_of_range
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс служит базовым для всех исключений, создаваемых для сообщения о том, что аргумент выходит за допустимый диапазон.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class out_of_range : public logic_error {  
public:  
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};  
```  
  
## <a name="remarks"></a>Заметки  
 Значение, возвращаемое [что](../standard-library/exception-class1.md) является копией **сообщение**`.`[данные](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Пример  
  
```  
// out_of_range.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
int main() {  
// out_of_range  
   try {  
      string str( "Micro" );  
      string rstr( "soft" );  
      str.append( rstr, 5, 3 );  
      cout << str << endl;  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
   };  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Caught: invalid string position  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< stdexcept>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Класс logic_error](../standard-library/logic-error-class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

