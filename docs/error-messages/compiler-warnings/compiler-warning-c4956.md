---
title: Предупреждение компилятора C4956 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac369ab3bbdd4afdfb5e8aa555770564f54732de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4956"></a>Предупреждение компилятора C4956
"тип": этот тип недоступен для проверки  
  
 Это предупреждение создается, если указано [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) , но код содержит тип, не подлежащий проверке.  
  
 Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .  
  
 В следующем примере возникает ошибка C4956.  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```