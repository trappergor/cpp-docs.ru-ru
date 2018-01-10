---
title: "Ошибка компилятора C2229 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2229
dev_langs: C++
helpviewer_keywords: C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 34add6428294d07a7dc1879bcbd10746a2a602d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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