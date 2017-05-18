---
title: "Класс bad_alloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::bad_alloc
- bad_alloc
dev_langs:
- C++
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3d42ce374744f446185466f65df77a38ebcdbfd4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="badalloc-class"></a>Класс bad_alloc
Данный класс описывает исключение, возникновение которого указывает на то, что запрос на выделение памяти не выполнен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>Примечания  
 Значение, возвращаемое **what**, — это определяемая в реализации строка C. Ни одна из функций-членов не создает исключение.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<new>  
  
 **Пространство имен:** std  
  
## <a name="example"></a>Пример  
  
```cpp  
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
 **Заголовок:** \<new>  
  
## <a name="see-also"></a>См. также
 [Класс exception](../standard-library/exception-class.md)  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


