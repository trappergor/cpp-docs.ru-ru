---
title: "C4936 Предупреждение компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 58d702067c186eeeea94768a03836b64577961ca
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4936"></a>Предупреждение компилятора C4936
Данный __declspec поддерживается только при компиляции с параметрами /clr или /clr:pure  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 Объект `__declspec` модификатор использовался, `__declspec` модификатор допустим только при компиляции с одним из [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) параметры.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) и [процесс](../../cpp/process.md).  
  
 C4936 всегда выдается как ошибка.  Вы можете отключить C4936 с [предупреждение](../../preprocessor/warning.md) pragma.  
  
 При компиляции следующего примера возникнет ошибка C4936:  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```
