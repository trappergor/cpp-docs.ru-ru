---
title: "Предупреждение компилятора C4957 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8eb7283942a8a89fc3322983c41c68082b6c5cee
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4957"></a>Предупреждение компилятора C4957
"приведение": явное приведение "исходный_тип" к "конечный_тип" недоступно для проверки  
  
 В результате приведения будет создан недоступный для проверки образ.  
  
 Некоторые приведения являются безопасными (например, приведение `static_cast` вызывает выполнение пользовательских преобразований и приведение `const_cast`). Объект [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) гарантированно создается проверяемый код.  
  
 Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается как ошибка и может быть отключено с [предупреждение](../../preprocessor/warning.md) pragma или [/wd](../../build/reference/compiler-option-warning-level.md) параметр компилятора.  
  
 Следующий пример приводит к возникновению предупреждения C4957:  
  
```  
// C4957.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4957 )  
using namespace System;  
int main() {  
   Object ^ o = "Hello, World!";  
   String ^ s = static_cast<String^>(o);   // C4957  
   String ^ s2 = safe_cast<String^>(o);   // OK  
}  
```
