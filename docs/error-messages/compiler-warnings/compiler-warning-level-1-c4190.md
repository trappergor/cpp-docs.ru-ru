---
title: Предупреждение (уровень 1) C4190 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e62f6bcfaa499338d5fde1d09cb91574241ce8a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4190"></a>Предупреждение (уровень 1) C4190 компилятора
«идентификатор1» имеет-компоновка, но возвращаемый тип UDT «идентификатор2» несовместим с языком Си  
  
 Функции или указатель функции имеет возвращаемый тип UDT (определяемый пользователем тип, который является класса, структуры, перечисления или объединения) и `extern` компоновку «C». Это допустимо если:  
  
-   Все вызовы этой функции происходят из C++.  
  
-   Определение функции находится в C++.  
  
## <a name="example"></a>Пример  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```