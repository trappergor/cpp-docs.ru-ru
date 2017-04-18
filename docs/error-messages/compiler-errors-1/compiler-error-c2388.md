---
title: "Ошибка компилятора ошибка C2388 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a11001dfa401b89c604e685524befd2c7a3c89d2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2388"></a>Ошибка компилятора C2388
«символ»: символ не может объявляться с обоих __declspec(appdomain) и \__declspec(process)  
  
 Одновременное использование модификаторов `appdomain` и `process``__declspec` для одного символа не допускается. Память для хранения переменной выделяется для каждого процесса или каждого домена приложений.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) и [процесс](../../cpp/process.md).  
  
 При компиляции следующего примера возникнет ошибка C2388:  
  
```  
// C2388.cpp  
// compile with: /clr /c  
__declspec(process) __declspec(appdomain) int i;   // C2388  
__declspec(appdomain) int i;   // OK  
```
