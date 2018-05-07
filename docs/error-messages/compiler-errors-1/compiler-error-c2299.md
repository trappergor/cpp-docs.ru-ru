---
title: Ошибка компилятора C2299 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2299
dev_langs:
- C++
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e21213f08e25050932274a64d0ed56db96f2a453
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2299"></a>Ошибка компилятора C2299
«функция»: изменение поведения: явная специализация не может быть конструктором копии или оператором назначения копии  
  
 Эта ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: предыдущие версии Visual C++ допускали явную специализацию для конструктора копий или оператор присваивания копии.  
  
 Чтобы устранить C2299, не всегда конструктор копий или оператор присваивания функции шаблона, но скорее не являющимся шаблоном функции, принимающей тип класса. Любой код, который вызывает конструктор копии или оператор присваивания, явно указав аргументы шаблона необходимо удалить аргументы шаблона.  
  
 Следующий пример приводит к возникновению ошибки C2299:  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```