---
title: Ошибка компилятора C2710 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2710
dev_langs:
- C++
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfc182527aeb349fb91d098133c4545b95a93ac2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2710"></a>Ошибка компилятора C2710
«конструктор»: «__declspec(модификатор)» может применяться только к функции, возвращающей указатель  
  
 Функция, возвращаемое значение является указателем является единственным конструкции, к которому `modifier` могут быть применены.  
  
 Следующий пример приводит к возникновению ошибки C2710:  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```