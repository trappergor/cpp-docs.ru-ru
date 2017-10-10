---
title: "Ошибка компилятора C2617 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2617
dev_langs:
- C++
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5e3272cb883469abbad5ee42538a7334ecd73d62
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2617"></a>Ошибка компилятора C2617
«функция»: несовместимый оператор return  
  
 Указанная функция не имеет объявленный тип возвращаемого значения, а предыдущий возвращаемое значение не предоставлено инструкции.  
  
 Следующий пример приводит к возникновению ошибки C2617:  
  
```  
// C2617.cpp  
int i;  
func() {   // no return type prototype  
   if( i ) return;   // no return value  
   else return( 1 );   // C2617 detected on this line  
}  
```  
  
 Возможное решение:  
  
```  
// C2617b.cpp  
// compile with: /c  
int i;  
int MyF() {  
   if (i)  
      return 0;  
   else   
      return (1);  
}  
```
