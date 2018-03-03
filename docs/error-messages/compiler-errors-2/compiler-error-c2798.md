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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4336577d3f2d1174dadb370db6001e982e9035f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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