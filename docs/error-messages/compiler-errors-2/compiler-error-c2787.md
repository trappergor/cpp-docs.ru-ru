---
title: Ошибка компилятора C2787 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6b45d27c295b37d859d6451281f52c166dc1691
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234630"
---
# <a name="compiler-error-c2787"></a>Ошибка компилятора C2787
«Идентификатор»: идентификатор GUID не была связана с этим объектом  
  
 [__Uuidof](../../cpp/uuidof-operator.md) оператор принимает определяемый пользователем тип с присоединенным идентификатором GUID или объект такого типа определяемых пользователем. Эта ошибка возникает, когда аргумент имеет определяемый пользователем тип, не сопоставлен идентификатор GUID.  
  
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