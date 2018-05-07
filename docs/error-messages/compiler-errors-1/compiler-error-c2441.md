---
title: Ошибка компилятора C2441 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6557e913f2bd34fda9d435d44020697a925af4e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2441"></a>Ошибка компилятора C2441
«переменная»: символ, объявленный с параметром __declspec(process), должен быть константой в/CLR: pure режим  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 По умолчанию переменные, домена приложения, в разделе **/CLR: pure**. Переменная, помеченная как `__declspec(process)` под **/CLR: pure** может привести к ошибкам, если изменения в одном домене приложения и чтение в другой.  
  
 Таким образом, поэтому компилятор применяет каждого процесса, переменные быть `const` под **/CLR: pure**, что делает их чтения только во всех доменах приложения.  
  
 Дополнительные сведения см. в разделе [процесс](../../cpp/process.md) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2441.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```