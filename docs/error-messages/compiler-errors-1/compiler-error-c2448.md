---
title: Ошибка компилятора C2448 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc62d7aeba0a128c9b736586e6c1502227de717
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2448"></a>Ошибка компилятора C2448
«Идентификатор»: инициализатор, использующий стиль функции, по-видимому, является определением функции  
  
 Неверное определение функции.  
  
 Эта ошибка может быть вызвана формальный список старого типа языка C.  
  
 Следующий пример приводит к возникновению ошибки C2448:  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```