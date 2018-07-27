---
title: Ошибка компилятора C3363 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3363
dev_langs:
- C++
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aec09769f4db4f501f62ebaa2a996dfdefb5fcd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254099"
---
# <a name="compiler-error-c3363"></a>Ошибка компилятора C3363
"тип": typeid можно применять только к типу  
  
 Неправильно использован оператор [typeid](../../windows/typeid-cpp-component-extensions.md) .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3363:  
  
```  
// C3363.cpp  
// compile with: /clr  
int main() {  
   System::typeid;   // C3363  
}  
```