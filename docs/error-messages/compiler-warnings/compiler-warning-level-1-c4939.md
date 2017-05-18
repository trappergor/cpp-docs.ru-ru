---
title: "Предупреждение (уровень 1) C4939 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 05b0e8b2864043fc086213c3df3e71e8215a9b31
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4939"></a>Предупреждение компилятора (уровень 1) C4939
\#Директива #pragma vtordisp является устаревшим и будет удален в будущих версиях Visual C++  
  
 [Vtordisp](../../preprocessor/vtordisp.md) pragma будет удален в будущих версиях Visual C++.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4939:  
  
```  
// C4939.cpp  
// compile with: /c /W1  
#pragma vtordisp(off)   // C4939  
```
