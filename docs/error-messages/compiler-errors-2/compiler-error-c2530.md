---
title: "Ошибка компилятора C2530 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7a5d6831c293f6ef25eb53cdfb6216f8142908d2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2530"></a>Ошибка компилятора C2530
«Идентификатор»: ссылки должны быть инициализированы  
  
 Следует инициализировать ссылку при ее объявлении, если она еще не объявлена:  
  
-   С помощью ключевого слова [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
-   Как член класса, структуры или объединения (и инициализации его конструктора).  
  
-   Как параметр в объявлении или определении функции.  
  
-   Возвращаемый тип функции.  
  
 Следующий пример приводит к возникновению ошибки C2530:  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```
