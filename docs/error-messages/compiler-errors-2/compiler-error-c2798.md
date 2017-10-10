---
title: "Ошибка компилятора C2798 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bb0a411651cf7c7f614942563baee5f04075fdf3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

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
