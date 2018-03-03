---
title: "Ошибка компилятора C2006 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4db382ab78cbd230813fada89f9c04244035932f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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