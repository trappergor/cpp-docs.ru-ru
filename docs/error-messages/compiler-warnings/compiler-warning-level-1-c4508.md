---
title: "Предупреждение (уровень 1) C4508 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a2d54a87565c3217168dc077f5aa79614fee080b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4508"></a>Предупреждение компилятора (уровень 1) C4508
«функция»: функция должна возвращать значение; предполагается, что тип возвращаемого значения «void»  
  
 Функция имеет возвращаемый тип не указан. В этом случае должны также вызывать C4430 и компилятор реализует исправления, предоставленным C4430 (значение по умолчанию — int).  
  
 Чтобы устранить это предупреждение, явно объявите тип возвращаемого значения функции.  
  
 Следующий пример приводит к возникновению ошибки C4508:  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```
