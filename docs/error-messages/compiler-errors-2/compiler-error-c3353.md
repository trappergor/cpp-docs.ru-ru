---
title: Ошибка компилятора C3353 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47c9d1dd8c21e56613b9da00fc2bf4f7fbeafcca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3353"></a>Ошибка компилятора C3353
delegate: создание делегата допускается только из глобальной функции или функции-члена управляемого типа или типа WinRT  
  
 Делегаты, объявленные с [делегировать](../../windows/delegate-cpp-component-extensions.md) ключевое слово, можно объявлять только в глобальной области видимости.  
  
 Следующий пример приводит к возникновению ошибки C3353:  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```