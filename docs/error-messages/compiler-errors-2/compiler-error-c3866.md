---
title: Ошибка компилятора C3866 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3866
dev_langs:
- C++
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da9109e35f3c79d33a4c3439aa58befdbe91068c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3866"></a>Ошибка компилятора C3866
отсутствует список аргументов функции вызова  
  
 Внутри нестатической функции-члена деструктора или метода завершения отсутствует список аргументов.  
  
 Следующий пример приводит к возникновению ошибки C3866:  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```