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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8d182e7a98d01dee4047defa5adb5ccc2dc7cde5
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2006"></a>Ошибка компилятора C2006
«Директива» вместо имени файла, найден «токен»  
  
 Директивы, такие как [#include](../../preprocessor/hash-include-directive-c-cpp.md) или [#import](../../preprocessor/hash-import-directive-cpp.md) должно использоваться имя файла. Чтобы устранить эту ошибку, убедитесь, что *маркера* является допустимым именем файла. Кроме того необходимо заключите имя файла в двойные кавычки или угловые скобки.  
  
 Следующий пример приводит к возникновению ошибки C2006:  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Возможное решение:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```
