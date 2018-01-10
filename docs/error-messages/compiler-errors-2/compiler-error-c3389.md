---
title: "Ошибка компилятора C3389 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3389
dev_langs: C++
helpviewer_keywords: C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd88753553d2bad1cb9253cfe709e7627c4b01ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3389"></a>Ошибка компилятора C3389
__declspec(Keyword) не может использоваться с параметром/clr: pure или/CLR: safe  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Объект [__declspec](../../cpp/declspec.md) подразумевает модификатор, используемый на состояние процесса.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) подразумевает на [appdomain](../../cpp/appdomain.md) состояния.  Поэтому при объявлении переменной с `keyword` **__declspec** модификатор и компиляции с **/CLR: pure** не допускается.  
  
 Следующий пример приводит к возникновению ошибки C3389:  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```