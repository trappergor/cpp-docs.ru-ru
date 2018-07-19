---
title: Предупреждение (уровень 3) C4290 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f03d35e1a3756979d8936647255e2b65afef56d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289897"
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