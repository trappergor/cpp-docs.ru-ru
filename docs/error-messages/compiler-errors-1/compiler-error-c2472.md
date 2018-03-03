---
title: "Ошибка компилятора C2472 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5267f20aaed4ebf1c320d3d960684376e29814ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2472"></a>Ошибка компилятора C2472
"функция" не может создаваться в управляемом коде "сообщение"; для генерации смешанного образа выполните компиляцию с параметром /clr  
  
 Эта ошибка возникает при использовании типов, не поддерживаемых в управляемом коде, в чистой среде CLR. Для устранения этой ошибки выполните компиляцию с параметром **/clr** .  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2472:  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [/ CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)