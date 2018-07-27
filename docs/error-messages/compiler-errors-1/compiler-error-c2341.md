---
title: Ошибка компилятора C2341 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc222129f3f12b5e7b5c6cb66e090907ff42a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197381"
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
  
 Возможное решение  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```