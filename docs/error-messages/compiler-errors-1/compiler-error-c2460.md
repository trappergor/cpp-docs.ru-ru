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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97ab5f3a2635bf25c01c2e54ba27c49447f1514a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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