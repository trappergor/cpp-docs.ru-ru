---
title: "Ошибка компилятора C3862 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af959252ce5b404d8646ad61e02c5e480b41ed83
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3862"></a>Ошибка компилятора C3862
«функция»: не удается скомпилировать неуправляемую функцию с параметром/clr: pure или/CLR: safe  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Компиляция с **/CLR: pure** или **/CLR: safe** может дать только изображение MSIL, изображение с без машинного (неуправляемого) кода.  Следовательно, нельзя использовать `unmanaged` pragma в **/CLR: pure** или **/CLR: safe** компиляции.  
  
 Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3862:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```
