---
title: Ошибка компилятора C2562 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2562
dev_langs:
- C++
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab3fd1a5eae008785a688bcbade674425fc8b2ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2562"></a>Ошибка компилятора C2562
«Идентификатор»: «void» функция, возвращающая значение  
  
 Функция, объявленная как `void` , но возвращает значение.  
  
 Эта ошибка может быть вызвана неверным прототипом функции.  
  
 Чтобы устранить эту ошибку, укажите тип возвращаемого значения в объявлении функции.  
  
 Следующий пример приводит к возникновению ошибки C2562:  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```