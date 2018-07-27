---
title: Ошибка компилятора C2537 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6100f77d3a1487bfa1eb12a78ac8187cec43fe64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199961"
---
# <a name="compiler-error-c2537"></a>Ошибка компилятора C2537
«спецификатор»: Недопустимая спецификация компоновки  
  
 Возможные причины:  
  
1.  Спецификатор компоновки не поддерживается. Поддерживается только спецификатор компоновки «C».  
  
2.  Компоновка «C» указано более одной функции в наборе перегруженных функций. Это не допускается.  
  
 Следующий пример приводит к возникновению ошибки C2537:  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```