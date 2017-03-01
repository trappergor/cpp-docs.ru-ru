---
title: "Ошибка компилятора C2441 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
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
ms.openlocfilehash: 1b98c85df0db4e947ceb5722715f5d020e1ecbec
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2441"></a>Ошибка компилятора C2441
«переменная»: символ, объявленный с директивой __declspec(process) должен быть const в/CLR: pure режим  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 По умолчанию переменные используются для каждого домена приложения в разделе **/CLR: pure**. Переменная, помеченная как `__declspec(process)` под **/CLR: pure** может привести к ошибкам, если изменения в одном домене приложения и прочитаны в другом.  
  
 Таким образом, поэтому компилятор применяет каждого процесса переменные быть `const` под **/CLR: pure**, что делает их чтения только во всех доменах приложения.  
  
 Дополнительные сведения см. в разделе [процесс](../../cpp/process.md) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2441.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```
