---
title: Ошибка компилятора C3641 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 496ff73822dcc1c886fbd2020f8ec6b8a5a9a2f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3641"></a>Ошибка компилятора C3641
«функция»: недопустимое соглашение о вызовах «соглашение_о_вызовах» для функции, скомпилированные с параметром/clr: pure или/CLR: safe  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Только [__clrcall](../../cpp/clrcall.md) соглашение о вызовах может использоваться с [/CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Следующий пример приводит к возникновению ошибки C3641:  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```