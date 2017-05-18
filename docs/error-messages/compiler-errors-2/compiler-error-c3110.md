---
title: "Ошибка компилятора C3110 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3110
dev_langs:
- C++
helpviewer_keywords:
- C3110
ms.assetid: 821dc71f-896e-4b2d-af0e-aa9932934b7b
caps.latest.revision: 7
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
ms.openlocfilehash: f6ada3a8894c8bc40c3821342a9a59911270029a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3110"></a>Ошибка компилятора C3110
«имя функции»: нельзя перегружать метод COM-интерфейса  
  
 Интерфейс, который стоит атрибут интерфейса, такие как:  
  
-   [пользовательский](../../windows/custom-cpp.md)  
  
-   [disp-интерфейс](../../windows/dispinterface.md)  
  
-   [Двойная](../../windows/dual.md)  
  
-   [object](../../windows/object-cpp.md)  
  
 не может быть перегружен. Например:  
  
```  
// C3110.cpp  
#include <unknwn.h>  
[ object, uuid= "4F98A180-EF37-11D1-978D-0000F805D73B" ]  
__interface ITestInterface  
{  
   HRESULT mf1(void);  
   HRESULT mf1(BSTR); // C3110  
};  
  
int main()  
{  
}  
```
