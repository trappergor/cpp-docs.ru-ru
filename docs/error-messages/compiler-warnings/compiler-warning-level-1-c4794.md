---
title: Ошибка компилятора предупреждение (уровень 1) C4794 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4794
dev_langs:
- C++
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88ffa1200e7c760f028549335f0df5a9ea8ba3d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4794"></a>Предупреждение компилятора (уровень 1) C4794
сегмент переменной из локальной памяти потока "переменная" изменен с "имя_раздела" на ".tls$"  
  
 Вы использовали [#pragma data_seg](../../preprocessor/data-seg.md) , чтобы поместить переменную tls в раздел, не начинающийся с ".tls$".  
  
 Раздел .tls$*x* раздел будет существовать в объектном файле, где определены переменные [__declspec(thread)](../../cpp/thread.md) . Раздел .tls в файле EXE или DLL будет получен из этих разделов.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C4794.  
  
```  
// C4794.cpp  
// compile with: /W1 /c  
#pragma data_seg(".someseg")  
__declspec(thread) int i;   // C4794  
  
// OK  
#pragma data_seg(".tls$9")  
__declspec(thread) int j;  
```