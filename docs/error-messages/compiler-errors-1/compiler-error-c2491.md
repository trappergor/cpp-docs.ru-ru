---
title: Ошибка компилятора C2491 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e46d63f6602af7fe962f8b139c93a4b9a561783
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198889"
---
# <a name="compiler-error-c2491"></a>Ошибка компилятора C2491
'идентификатор' : определение функции dllimport не разрешено  
  
 Данные, статические данные-члены могут быть объявлены, как `dllimport`, но не определены как `dllimport`.  
  
 Чтобы устранить эту проблему, удалите описатель `__declspec(dllimport)` из определения функции.  
  
 Следующий пример приводит к возникновению ошибки C2491:  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```