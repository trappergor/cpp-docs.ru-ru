---
title: Ошибка компилятора C2798 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de30a19a2a27cde991cfce0ca061ce6f5447f033
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2798"></a>Ошибка компилятора C2798
«super::member» является неоднозначным  
  
 Несколько унаследованных структур содержат член, на который существует ссылка [super](../../cpp/super.md). Невозможно исправить ошибку, либо:  
  
-   Удаление B1 или В2 из списка наследования D.  
  
-   Изменение имени члена данных в B1 или В2.  
  
 Следующий пример приводит к возникновению ошибки C2798:  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```