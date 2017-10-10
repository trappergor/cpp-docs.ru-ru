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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ed41a3d78ab9652d1e88ceefe29011eb5b2225a4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
