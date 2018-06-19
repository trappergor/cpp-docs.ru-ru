---
title: Предупреждение (уровень 1) C4508 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f152c2f3573e5f3bd7b8e9be0603ed6d3f11bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283200"
---
# <a name="compiler-warning-level-1-c4508"></a>Предупреждение компилятора (уровень 1) C4508
«функция»: функция должна возвращать значение; предполагается, что тип возвращаемого значения «void»  
  
 Функция имеет возвращаемый тип не указан. В этом случае должен также инициировать C4430 и компилятор реализует устранения этой проблемы, о которых сообщили C4430 (значение по умолчанию — int).  
  
 Чтобы устранить это предупреждение, необходимо явно объявите тип возвращаемого значения функции.  
  
 Следующий пример приводит к возникновению ошибки C4508:  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```