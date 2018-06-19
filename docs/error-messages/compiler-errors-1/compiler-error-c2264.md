---
title: Ошибка компилятора C2264 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2264
dev_langs:
- C++
helpviewer_keywords:
- C2264
ms.assetid: 158b72cc-cee9-4a08-bd79-b7a5955345a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8942c5537e7129c5ecd8b8ac6956fdd6c9e1efaa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168949"
---
# <a name="compiler-error-c2264"></a>Ошибка компилятора C2264
«функция»: ошибка в определении функции или объявление; функция не вызвана  
  
 Функция не может вызываться из-за неверного определения или объявления.  
  
 Следующий пример приводит к возникновению ошибки C2264:  
  
```  
// C2264.cpp  
struct C {  
   // Delete the following line to resolve.  
   operator int(int = 0){}   // incorrect declaration  
};  
  
struct D {  
   operator int(){return 0;}   // OK  
};  
  
int main() {  
   int i;  
  
   C c;  
   i = c;   // C2264  
  
   D d;  
   i = d;   // OK  
}  
```