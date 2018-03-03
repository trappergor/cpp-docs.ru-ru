---
title: "Ошибка компилятора C2812 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12ab4a753ad2098dfa4c3bccb2190c18bcc2fafb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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