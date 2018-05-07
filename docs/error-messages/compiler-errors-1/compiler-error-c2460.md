---
title: Ошибка компилятора C2460 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4220be654f93ecd79d196efc14657ca7346411f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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