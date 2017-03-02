---
title: "Предупреждение компилятора (уровень 1) C4399 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
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
ms.openlocfilehash: 7d7584e318a42530a2a91fee4b428c92bfaf120c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4399"></a>Предупреждение компилятора (уровень 1) C4399
«символ»: символ для каждого процесса не следует помечать с __declspec(dllimport) при компиляции с параметром/clr: pure  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 Данные из собственного изображения или машинный код и конструкций среды CLR не удалось импортировать в чистом образе. Чтобы устранить это предупреждение, компиляция с **/CLR** (не **/CLR: pure**) или удалить `__declspec(dllimport)`.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4399.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```
