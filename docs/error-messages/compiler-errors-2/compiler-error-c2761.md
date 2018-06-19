---
title: Ошибка компилятора C2761 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2761
dev_langs:
- C++
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62c505b5219cb76ad83c3b6ece13e7d10f16e555
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236576"
---
# <a name="compiler-error-c2761"></a>Ошибка компилятора C2761
«функция»: член повторное объявление функции не допускается  
  
 Невозможно повторно объявить функцию-член. Можно определять, но не его повторного объявления.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2761.  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## <a name="example"></a>Пример  
 Невозможно определить нестатические члены класса или структуры.  Следующий пример приводит к возникновению ошибки C2761.  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```