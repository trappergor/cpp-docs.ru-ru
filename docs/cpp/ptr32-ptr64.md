---
title: "__ptr32 __ptr64 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d722f8403efbe1172fefbe8a792c95d4063e893f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 `__ptr32` представляет собственный указатель в 32-разрядной системе, а `__ptr64` представляет собственный указатель в 64-разрядной системе.  
  
 В следующем примере показано, как объявить каждый из этих типов указателей.  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 В 32-разрядной системе указатель, объявленный с помощью `__ptr64`, усекается до 32-разрядного указателя. В 64-разрядной системе указатель, объявленный с помощью `__ptr32`, приводится к 64-разрядному указателю.  
  
> [!NOTE]
>  Нельзя использовать `__ptr32` или `__ptr64` при компиляции с параметром **/CLR: pure**. В противном случае создается ошибка `Compiler Error C2472`. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как объявить и выделить указатели с ключевыми словами `__ptr32` и `__ptr64`.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
```Output  
32  
64  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Базовые типы](../cpp/fundamental-types-cpp.md)
