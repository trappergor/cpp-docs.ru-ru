---
title: "Ошибка компилятора C2785 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a545935e06d958502fb3b97cb8969f92172ca6b6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2785"></a>Ошибка компилятора C2785
«объявление1» и «объявление2» имеют различные возвращаемые типы  
  
 Тип возвращаемого значения специализации шаблона функции отличается от возвращаемого типа шаблона основной функции.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте все специализации шаблона функции для обеспечения согласованности.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2785:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```
