---
title: "Класс bad_alloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::bad_alloc"
  - "new/std:bad_alloc"
  - "bad_alloc"
  - "std.bad_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_alloc - класс"
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# Класс bad_alloc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, возникновение которого указывает на то, что запрос на выделение памяти не выполнен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>Заметки  
 Значение, возвращаемое **что** является строка C конкретной реализации. Ни одна из функций-членов не создает исключение.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< new>  
  
 **Пространство имен:** std  
  
## <a name="example"></a>Пример  
  
```  
// bad_alloc.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
using namespace std;  
  
int main() {  
   char* ptr;  
   try {  
      ptr = new char[(~unsigned int((int)0)/2) - 1];  
      delete[] ptr;  
   }  
   catch( bad_alloc &ba) {  
      cout << ba.what( ) << endl;  
   }  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
bad allocation  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< new>  
  
## <a name="see-also"></a>См. также
 [Класс Exception](../standard-library/exception-class1.md)  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

