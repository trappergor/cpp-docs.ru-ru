---
title: Ошибка компилятора предупреждение (уровень 3) C4645 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4645
dev_langs:
- C++
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718afb6b8336e36e0c0244cbdccd8af16ac4167f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292913"
---
# <a name="compiler-warning-level-3-c4645"></a>Предупреждение компилятора (уровень 3) C4645
функция, объявленная с атрибутом __declspec(noreturn) имеет оператор return  
  
 A [return](../../cpp/return-statement-in-program-termination-cpp.md) найден в функции, помеченной модификатором [noreturn](../../cpp/noreturn.md) `__declspec` . Оператор `return` был пропущен.  
  
 Следующий пример приводит к возникновению ошибки C4645.  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```