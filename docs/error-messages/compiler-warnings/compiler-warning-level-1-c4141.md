---
title: Предупреждение (уровень 1) C4141 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4141
dev_langs:
- C++
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6580557a5713bc7f7faf5e0e086081dcc156d5af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4141"></a>Предупреждение компилятора (уровень 1) C4141
"модификатор" используется несколько раз  
  
## <a name="example"></a>Пример  
  
```  
// C4141.cpp  
// compile with: /W1 /LD  
inline inline void func ();   // C4141  
```