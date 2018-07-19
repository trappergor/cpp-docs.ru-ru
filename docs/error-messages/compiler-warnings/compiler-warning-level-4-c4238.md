---
title: Предупреждение (уровень 4) C4238 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06dbec01da8d1b47cb7b93c90a22ae5266e9b4c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292442"
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