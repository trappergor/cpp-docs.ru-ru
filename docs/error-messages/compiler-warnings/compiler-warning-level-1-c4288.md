---
title: "Предупреждение (уровень 1) C4288 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4288
dev_langs: C++
helpviewer_keywords: C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abbc9ba0a41a4961c49cffca6c10ff9a4e4e1437
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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