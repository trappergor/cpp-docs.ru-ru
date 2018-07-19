---
title: Предупреждение (уровень 1) C4939 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 459674bb4e6899563a18943f7ba510a6168d0e28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296888"
---
# <a name="compiler-warning-level-1-c4939"></a>Предупреждение компилятора (уровень 1) C4939
\#Директива #pragma vtordisp является устаревшим и будет удален в будущих версиях Visual C++  
  
 Директива pragma [vtordisp](../../preprocessor/vtordisp.md) будет удалена в будущих выпусках Visual C++.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4939:  
  
```  
// C4939.cpp  
// compile with: /c /W1  
#pragma vtordisp(off)   // C4939  
```