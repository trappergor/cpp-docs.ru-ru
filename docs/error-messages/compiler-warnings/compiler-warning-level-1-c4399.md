---
title: Предупреждение компилятора (уровень 1) C4399 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b39f4919dd736e4bf2e6230fe68ea69c2b14766e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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