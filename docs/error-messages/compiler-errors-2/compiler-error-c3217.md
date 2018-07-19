---
title: Ошибка компилятора C3217 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3217
dev_langs:
- C++
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb8ee0f6e00ac1bfb2ad531f2236bb2d9208d27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251298"
---
# <a name="compiler-error-c3217"></a>Ошибка компилятора C3217
"параметр": универсальный параметр нельзя ограничить в этом объявлении  
  
 Ограничение неправильно сформировано; универсальный параметр ограничения должен соответствовать параметру шаблона универсального класса.  
  
 При компиляции следующего примера возникнет ошибка C3217:  
  
```  
// C3217.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
ref class C {  
   generic <class T1>  
   where T : A   // C3217  
   void f();  
};  
```  
  
 В следующем примере показано возможное решение:  
  
```  
// C3217b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
ref class C {  
   generic <class T1>  
   where T1 : A  
   void f();  
};  
```