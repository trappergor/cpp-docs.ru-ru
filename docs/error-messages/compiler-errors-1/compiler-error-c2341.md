---
title: "Ошибка компилятора C2341 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5460ff70c95fd593539a16140c52fa1490bffc4e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2341"></a>Ошибка компилятора C2341
» Имя раздела: сегмент должен быть определен с помощью #pragma data_seg, code_seg или предыдущего раздела, для использования  
  
 [Выделить](../../cpp/allocate.md) Инструкция ссылается на еще не определен сегмент [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), или [раздел](../../preprocessor/section.md) директивы pragma.  
  
 Следующий пример приводит к возникновению ошибки C2341:  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 Возможное решение:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```
