---
title: "Ошибка компилятора C2601 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2601
dev_langs:
- C++
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a47e86aa85722bac62545d84792670df69038bfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2601"></a>Ошибка компилятора C2601
«функция»: недопустимые локальные определения функций  
  
 Код пытается определить функции внутри функции.  
  
 Или, в исходном коде перед ошибки C2601 может быть дополнительный фигурную скобку.  
  
 Следующий пример приводит к возникновению ошибки C2601:  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```