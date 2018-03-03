---
title: "Ошибка компилятора C2434 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 848a0063cc50eefc76a7c635f7a6f69a0a8b996f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2434"></a>Ошибка компилятора C2434
«символ»: символ, объявленный с параметром __declspec(process), невозможно динамически инициализировать в/CLR: pure режим  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Невозможно динамически инициализировать внутрипроцессную переменную в списке **/CLR: pure**. Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [процесс](../../cpp/process.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2434.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```