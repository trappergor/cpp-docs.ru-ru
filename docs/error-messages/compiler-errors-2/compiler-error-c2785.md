---
title: "Ошибка компилятора C2785 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2785
dev_langs: C++
helpviewer_keywords: C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9587151175c593e4b1d9d30f45a19ce807c24990
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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