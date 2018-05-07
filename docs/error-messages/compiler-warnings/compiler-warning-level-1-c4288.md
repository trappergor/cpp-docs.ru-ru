---
title: Предупреждение (уровень 1) C4288 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c51bdc201b364d76f1692db8ee14973c90923f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4288"></a>Предупреждение компилятора (уровень 1) C4288
использовано нестандартное расширение: «переменная»: переменная управления циклом, объявленная в цикле for, используется вне области цикла; это противоречит объявлению во внешней области  
  
 При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc: forScope**, переменной, объявленной в **для** цикла использовался после [для](../../cpp/for-statement-cpp.md)-области видимости цикла. Расширение Microsoft для языка C++ позволяет данной переменной оставаться в области видимости и C4288 напоминает, что первое объявление переменной не используется.  
  
 В разделе [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) сведения о способах указания расширения Microsoft в **для** циклы с параметром/Ze.  
  
 Следующий пример приводит к возникновению ошибки C4288:  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```