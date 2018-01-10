---
title: "Ошибка компилятора C2441 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2441
dev_langs: C++
helpviewer_keywords: C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 645e06a0685f00359d468a4a4b9bd3522921b511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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