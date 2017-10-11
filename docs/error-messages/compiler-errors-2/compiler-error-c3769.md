---
title: "Ошибка компилятора C3769 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 097b12ca4cdca8f465fd5383e42609187b66d32e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3769"></a>Ошибка компилятора C3769
«Тип»: вложенный класс не может иметь имя, совпадающее с именем немедленно включающего класса  
  
 Вложенный класс не может иметь имя, совпадающее с именем немедленно включающего класса.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3769.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```
