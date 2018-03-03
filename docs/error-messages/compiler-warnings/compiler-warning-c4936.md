---
title: "Предупреждение компилятора C4936 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 995cd7b2b774b768d6bccf10ddcec18101580e74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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