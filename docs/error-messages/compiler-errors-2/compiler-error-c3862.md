---
title: "Ошибка компилятора C3862 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 48dbae62c367616a437db0607d84fa89e8006021
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3862"></a>Ошибка компилятора C3862
«функция»: не удается скомпилировать неуправляемой функции с параметром/clr: pure или/CLR: safe  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 Компиляция с помощью **/CLR: pure** или **/CLR: safe** может дать только изображение MSIL, изображение с без машинного (неуправляемого) кода.  Следовательно, нельзя использовать `unmanaged` прагма-директиву **/CLR: pure** или **/CLR: safe** компиляции.  
  
 Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3862:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```
