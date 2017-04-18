---
title: "Предупреждение компилятора C4959 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4959
dev_langs:
- C++
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f7cde1151bd220415b950dcce089265be118de34
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4959"></a>Предупреждение компилятора C4959
не удается определить неуправляемую структуру "тип" в /clr:safe, поскольку доступ к ее членам выдает код, недоступный для проверки  
  
 Обращение к члену неуправляемого типа приводит к формированию непроверяемого (peverify.exe) образа.  
  
 Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается как ошибка и может быть отключено с [предупреждение](../../preprocessor/warning.md) pragma или [/wd](../../build/reference/compiler-option-warning-level.md) параметр компилятора.  
  
 Следующий пример приводит к возникновению предупреждения C4959:  
  
```  
// C4959.cpp  
// compile with: /clr:safe  
  
// Uncomment the following line to resolve.  
// #pragma warning( disable : 4959 )  
struct X {  
   int data;  
};  
  
int main() {  
   X x;  
   x.data = 10;   // C4959  
}  
```
