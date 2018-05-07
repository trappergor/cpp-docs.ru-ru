---
title: Предупреждение (уровень 3) C4334 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f26749c968c3cac18b509046633ba3d91d15a4be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4334"></a>Предупреждение компилятора (уровень 3) C4334
«оператор»: результат 32-разрядного смещения неявно преобразуется в 64 бита (предполагалось 64-разрядное смещение?)  
  
 Результат 32-разрядного смещения неявно преобразовано в 64-разрядный, а компилятор предполагает, что 64-разрядное смещение был предназначен.  Чтобы устранить это предупреждение, используйте 64-разрядный сдвиг или явно привести результат сдвига к 64-разрядной.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4334.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```