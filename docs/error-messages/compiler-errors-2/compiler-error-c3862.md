---
title: "Ошибка компилятора C3862 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3862"
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция: неуправляемую функцию невозможно компилировать с параметрами \/clr:pure или \/clr:safe  
  
 Компиляция при помощи **\/clr:pure** or **\/clr:safe** может дать только изображение MSIL, изображение с немашинным \(неуправляемым\) кодом.  Следовательно, нельзя использовать директиву pragma `unmanaged` в компиляции **\/clr:pure** или **\/clr:safe** .  
  
 Дополнительные сведения см. в разделах [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) и [managed, unmanaged](../../preprocessor/managed-unmanaged.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3862:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```