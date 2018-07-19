---
title: Ошибка компилятора C2006 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93880e7d767de3101cd7a292af5fa2874cae86bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165575"
---
# <a name="compiler-error-c2006"></a>Ошибка компилятора C2006
«Директива» вместо имени файла, найден «токен»  
  
 Директивы, такие как [#include](../../preprocessor/hash-include-directive-c-cpp.md) или [#import](../../preprocessor/hash-import-directive-cpp.md) должно использоваться имя файла. Чтобы устранить эту ошибку, убедитесь, что *маркера* является допустимым именем файла. Кроме того необходимо заключите имя файла в двойные кавычки или угловые скобки.  
  
 Следующий пример приводит к возникновению ошибки C2006:  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Возможное решение  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```