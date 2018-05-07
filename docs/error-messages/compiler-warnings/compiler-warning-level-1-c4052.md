---
title: Ошибка компилятора предупреждение (уровень 1) C4052 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4052
dev_langs:
- C++
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5c937e602f14789419f6b124034503c127f6dc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4052"></a>Предупреждение компилятора (уровень 1) C4052
объявления функции отличаются; одно из них содержит переменные аргументы  
  
 Одно объявление функции не содержит переменных аргументов. Игнорируется.  
  
 В следующем примере возникает ошибка C4052.  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```