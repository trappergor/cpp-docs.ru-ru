---
title: "Ошибка компилятора C2008 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: 7
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: fc0efbbb942c689831dae73b14f2fa113bec997a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2008"></a>Ошибка компилятора C2008
"символ": не требуется в макроопределении  
  
 Символ расположен сразу после имени макроса. Чтобы устранить эту ошибку, должен вводиться пробел после имени макроса.  
  
 Следующий пример приводит к возникновению ошибки C2008:  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Возможное решение:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```
