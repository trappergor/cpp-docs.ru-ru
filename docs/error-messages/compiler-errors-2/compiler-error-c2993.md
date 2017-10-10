---
title: "Ошибка компилятора C2993 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6306b2c3c632d25ee6b37a025516f759cc126a6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2993"></a>Ошибка компилятора C2993
«Идентификатор»: недопустимый тип для параметра шаблона не является типом «параметр»  
  
 Нельзя объявить шаблон с аргументом структуры или объединения. Используйте указатели для передачи структур и объединений в качестве параметров шаблона.  
  
 Следующий пример приводит к возникновению ошибки C2993:  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Эта ошибка может также возникать в результате изменений работы компилятора в Visual Studio .NET 2003: с плавающей точкой, не являющийся типом параметров не допускается. Стандарт C++ не допускает чисел с плавающей запятой параметров шаблона, не являющегося типом.  
  
 Если шаблон функции, используйте аргумент функции для передачи в параметр с плавающей точки не являющийся типом параметра (этот код будет допустим в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET). Если это шаблон класса, легко решение отсутствует.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```
