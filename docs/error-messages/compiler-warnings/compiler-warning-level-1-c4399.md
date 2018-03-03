---
title: "Предупреждение компилятора (уровень 1) C4399 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eff01c29d423b0823b41bf63702cf42ee839a523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4399"></a>Предупреждение компилятора (уровень 1) C4399
«символ»: символ для каждого процесса не следует помечать с помощью __declspec(dllimport) при компиляции с параметром/clr: pure  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 Данные из образа в машинном коде с или изображение машинного кода и конструкции среды CLR не будут импортированы в чистом образе. Чтобы устранить это предупреждение, компиляция с **/CLR** (не **/CLR: pure**) или удалить `__declspec(dllimport)`.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4399.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```