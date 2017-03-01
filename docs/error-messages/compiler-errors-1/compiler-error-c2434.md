---
title: "Ошибка компилятора C2434 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
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
ms.openlocfilehash: 65aac590a3282f2fd71c460d14927f5695fcdc5a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2434"></a>Ошибка компилятора C2434
«символ»: символ, объявленный с директивой __declspec(process) не может инициализироваться динамически в/CLR: pure режим  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 Невозможно динамически инициализировать внутрипроцессную переменную в разделе **/CLR: pure**. Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [процесс](../../cpp/process.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2434.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```
