---
title: "Предупреждение (уровень 3) C4290 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4290
dev_langs: C++
helpviewer_keywords: C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70a278cb3e660e89e1aba067cab9c20aacf8f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4290"></a>Предупреждение компилятора (уровень 3) C4290
Спецификация исключений C++ игнорируется, кроме функции не является __declspec(nothrow)  
  
 Функция объявляется с помощью спецификации исключений, которые принимает Visual C++, но не реализует. Код с исключением, может потребоваться повторная компиляция спецификации, которые учитываются во время компиляции и ссылку для его использования в будущих версиях, поддерживающих спецификации исключений.  
  
 Дополнительные сведения см. в разделе [спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md) .  
  
 Это предупреждение можно избежать, используя [предупреждение](../../preprocessor/warning.md) директивы pragma:  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 В следующем образце кода приводит к возникновению ошибки C4290:  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```