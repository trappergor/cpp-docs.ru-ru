---
title: Ошибка компилятора C2812 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28d46b0f9744f192d677d7b2df27b67e734de1b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2812"></a>Ошибка компилятора C2812
\#Импорт не поддерживается с параметром/clr: pure и/CLR: safe  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 [директива #import](../../preprocessor/hash-import-directive-cpp.md) не поддерживается с **/CLR: pure** и **/CLR: safe** из-за `#import` требует использования библиотек поддержки собственного компилятора.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2812.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```