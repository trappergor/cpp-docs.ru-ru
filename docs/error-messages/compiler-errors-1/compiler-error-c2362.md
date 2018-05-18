---
title: Ошибка компилятора C2362 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53b0b77930acba6ecf2d0f3c6748ba52e9b28e0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2362"></a>Ошибка компилятора C2362
Пропуск инициализации «идентификатор», «goto "Метка»  
  
 При компиляции с параметром [/Za](../../build/reference/za-ze-disable-language-extensions.md), перехода к метке предотвращает инициализацию идентификатор.  
  
 Не удается переход после объявления с инициализатором, если объявление содержится в блоке, не будут сохранены или переменная уже инициализирован.  
  
 При компиляции следующего примера возникнет ошибка C2326:  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 Возможное решение  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```