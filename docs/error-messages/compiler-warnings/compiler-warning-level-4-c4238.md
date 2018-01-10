---
title: "Предупреждение (уровень 4) C4238 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4238
dev_langs: C++
helpviewer_keywords: C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e8e52868d97d31243f92307e9bfd158c818c2f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4238"></a>Предупреждение компилятора (уровень 4) C4238
использовано нестандартное расширение: значение rvalue класса использовано как значение lvalue  
  
 Для обеспечения совместимости с предыдущими версиями Visual C++ расширения Microsoft (**/Ze**) позволяют использование типа класса как значение rvalue в контексте, который явно или неявно принимает его адрес. В некоторых случаях, как показано в примере ниже это может быть опасно.  
  
## <a name="example"></a>Пример  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Такое использование приводит к ошибке в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).