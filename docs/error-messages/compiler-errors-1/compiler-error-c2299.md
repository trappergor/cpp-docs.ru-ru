---
title: "Ошибка компилятора C2299 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2299
dev_langs: C++
helpviewer_keywords: C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8190511605a7f01dc399e1d8a8b4af96477fa407
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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