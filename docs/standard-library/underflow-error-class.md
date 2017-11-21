---
title: "Класс underflow_error | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdexcept/std::underflow_error
dev_langs: C++
helpviewer_keywords: underflow_error class
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 253225c8fd47db746472b7e05169fb73dee963bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="underflowerror-class"></a>Класс underflow_error
Этот класс служит базовым для всех исключений, создаваемых для сообщения об арифметической неточности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class underflow_error : public runtime_error {  
public:  
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Примечания  
 Значение, возвращаемое [what](../standard-library/exception-class.md), — это копия **данных**`.`[сообщения](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Пример  
  
```cpp  
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
 **Заголовок:** \<stdexcept>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<Члены stdexcept>](http://msdn.microsoft.com/en-us/7b6b0a73-916e-44aa-9a3f-f5b6b3ce98e6)   
 [Класс runtime_error](../standard-library/runtime-error-class.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

