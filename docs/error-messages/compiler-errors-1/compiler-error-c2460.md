---
title: "Ошибка компилятора C2460 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 00e4015a0dae5054973ba72bb0e4f89c7443ae03
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2460"></a>Ошибка компилятора C2460
«идентификатор1»: использует «идентификатор2», который определяется  
  
 Класс или структура (`identifier2`) объявляется как член самого себя (`identifier1`). Не разрешены рекурсивные определения классов и структур.  
  
 Следующий пример приводит к возникновению ошибки C2460:  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 Вместо этого используйте ссылку на указатель в классе.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```
