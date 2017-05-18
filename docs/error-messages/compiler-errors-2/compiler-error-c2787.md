---
title: "Ошибка компилятора C2787 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
caps.latest.revision: 10
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
ms.openlocfilehash: d421b339df28bcccdfcba2c9b297f1cd5a16915d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2787"></a>Ошибка компилятора C2787
«Идентификатор»: идентификатор GUID не была связана с этим объектом  
  
 [__Uuidof](../../cpp/uuidof-operator.md) оператор принимает определяемый пользователем тип с присоединенным идентификатором GUID или объект такого типа определяемых пользователем. Эта ошибка возникает, когда аргумент имеет определяемый пользователем тип не сопоставлен идентификатор GUID.  
  
 Следующий пример приводит к возникновению ошибки C2787:  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```
