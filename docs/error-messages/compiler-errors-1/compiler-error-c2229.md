---
title: "Ошибка компилятора C2229 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c54e3affb39cb396df1caaafe6450d5c6ac80f6e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2229"></a>Ошибка компилятора C2229
тип «идентификатор» имеет недопустимый массив нулевого размера  
  
 Член структуры или битовое поле содержит массив нулевого размера, который не является последним элементом.  
  
 Поскольку имеется массив нулевого размера в качестве последнего члена структуры при распределении структуры необходимо указать его размер.  
  
 Если массив нулевого размера не является последним элементом структуры, компилятор не может вычислить смещение для оставшихся полей.  
  
 Следующий пример приводит к возникновению ошибки C2229:  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```
