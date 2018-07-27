---
title: Ошибка компилятора C2785 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc0ca6235e0fd4bdd22330e807464e96280ae461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234033"
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