---
title: "Предупреждение компилятора C4956 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 782735be55c043482679740afa9571ba7b29dfc4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4956"></a>Предупреждение компилятора C4956
"тип": этот тип недоступен для проверки  
  
 Это предупреждение возникает, когда [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) указан и ваш код содержит тип, не подлежащий проверке.  
  
 Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается как ошибка и может быть отключено с [предупреждение](../../preprocessor/warning.md) pragma или [/wd](../../build/reference/compiler-option-warning-level.md) параметр компилятора.  
  
 В следующем примере возникает ошибка C4956.  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```
