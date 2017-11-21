---
title: "Предупреждение компилятора C4957 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4957
dev_langs: C++
helpviewer_keywords: C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c43ddf0e336d9964d08939bb7c1dd145caf6c848
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4957"></a>Предупреждение компилятора C4957
"приведение": явное приведение "исходный_тип" к "конечный_тип" недоступно для проверки  
  
 В результате приведения будет создан недоступный для проверки образ.  
  
 Некоторые приведения являются безопасными (например, приведение `static_cast` вызывает выполнение пользовательских преобразований и приведение `const_cast`). При выполнении приведения [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) гарантированно создается проверяемый код.  
  
 Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .  
  
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