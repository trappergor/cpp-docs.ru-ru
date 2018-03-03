---
title: "Ошибка компилятора C2881 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2881
dev_langs:
- C++
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6f34c3f48e90ce773f23068bd7f0b3712197ec9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2881"></a>Ошибка компилятора C2881
пространство имен «1»: уже используется в качестве псевдонима для пространства имен «2»  
  
 То же имя нельзя использовать в качестве псевдонима для двух пространств имен.  
  
 Следующий пример приводит к возникновению ошибки C2881:  
  
```  
// C2881.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
namespace B {  
   int i;  
}  
  
namespace C = A;  
namespace C = B;   // C2881 C is already an alias for A  
```