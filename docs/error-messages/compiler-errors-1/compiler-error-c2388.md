---
title: "Ошибка компилятора C2388 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2388
dev_langs: C++
helpviewer_keywords: C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa9f970d71be7b19551ef5029df49b696eb353e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2388"></a>Ошибка компилятора C2388
«символ»: символ не может объявляться с обоих __declspec(appdomain) и \__declspec(process)  
  
 Одновременное использование модификаторов `appdomain` и `process` `__declspec` для одного символа не допускается. Память для хранения переменной выделяется для каждого процесса или каждого домена приложений.  
  
 Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).  
  
 При компиляции следующего примера возникнет ошибка C2388:  
  
```  
// C2388.cpp  
// compile with: /clr /c  
__declspec(process) __declspec(appdomain) int i;   // C2388  
__declspec(appdomain) int i;   // OK  
```