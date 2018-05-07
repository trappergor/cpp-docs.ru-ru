---
title: Предупреждение (уровень 2) C4307 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4307
dev_langs:
- C++
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52914fc5825bda5647308c006b853538f3d6225e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4307"></a>Предупреждение компилятора (уровень 2) C4307
«оператор»: переполнение целой константы  
  
 Оператор, используемый в выражении возникает переполнение памяти, выделенной для него целой константы. Может потребоваться использовать больший тип константы. Объект **типа signed int** содержит меньше, чем значение `unsigned int` из-за **типа signed int** один бит используется для представления знака.  
  
 Следующий пример приводит к возникновению ошибки C4307:  
  
```  
// C4307.cpp  
// compile with: /W2  
int i = 2000000000 + 2000000000;   // C4307  
int j = (unsigned)2000000000 + 2000000000;   // OK  
  
int main()  
{  
}  
```