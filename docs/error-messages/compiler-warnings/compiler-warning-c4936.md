---
title: Предупреждение компилятора C4936 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcf9f32a4a1b1e43cb4bd69c754e3ae3a98bff3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4936"></a>Предупреждение компилятора C4936
Данный __declspec поддерживается только при компиляции с параметрами /clr или /clr:pure  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 Использовался модификатор `__declspec` , но модификатор `__declspec` допустим только при компиляции с одним из параметров [/clr](../../build/reference/clr-common-language-runtime-compilation.md) .  
  
 Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).  
  
 C4936 всегда выдается как ошибка.  Вы можете отключить C4936 с помощью директивы [warning](../../preprocessor/warning.md) .  
  
 При компиляции следующего примера возникнет ошибка C4936:  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```