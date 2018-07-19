---
title: Ошибка компилятора C2647 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2647
dev_langs:
- C++
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca5de79746876a60cc9a64c4bf8f91e468b4d379
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232624"
---
# <a name="compiler-error-c2647"></a>Ошибка компилятора C2647
«оператор»: Невозможно разыменовать «тип1» в «тип2»  
  
 Левый операнд оператора указателя на член ( `->*` или `.*` ) не может быть неявно преобразован в тип, относящийся к правому оператору.  
  
 Следующий пример приводит к возникновению ошибки C2647:  
  
```  
// C2647.cpp  
class C {};  
class D {};  
  
int main() {  
   D d, *pd;  
   C c, *pc = 0;  
   int C::*pmc = 0;  
   pd->*pmc = 0;   // C2647  
   d.*pmc = 0;   // C2647  
  
   // OK  
   pc->*pmc = 0;  
   c.*pmc = 0;  
}  
```