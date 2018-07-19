---
title: Предупреждение (уровень 1) C4804 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4804
dev_langs:
- C++
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 677899230b2475c80f9bdd461a0c79740c4d3bec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286985"
---
# <a name="compiler-warning-level-1-c4804"></a>Предупреждение компилятора (уровень 1) C4804
«Операция»: небезопасное использование типа «bool» в операции  
  
 Это предупреждение предназначено для при использовании `bool` переменной или непредвиденным образом. Например, предупреждение C4804 возникает при использовании операторов, таких как отрицательный унарный оператор (**-**) или оператор дополнения (`~`). Компилятор вычисляет выражение.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4804:  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```