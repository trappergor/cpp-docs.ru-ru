---
title: Ошибка компилятора C2008 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88dcbc88b50ee46b406d383ec36e1fed167eca05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165523"
---
# <a name="compiler-error-c2008"></a>Ошибка компилятора C2008
"символ": не требуется в макроопределении  
  
 Символ расположен сразу после имени макроса. Чтобы устранить эту ошибку, должен быть пробел после имени макроса.  
  
 Следующий пример приводит к возникновению ошибки C2008:  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Возможное решение  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```