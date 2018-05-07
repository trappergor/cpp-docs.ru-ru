---
title: Предупреждение (уровень 3) C4018 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4018
dev_langs:
- C++
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb784c8a368b5f5836deaff17d07542519ba980
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4018"></a>Предупреждение (уровень 3) C4018 компилятора
«выражение»: несоответствие со знаком и без  
  
 Сравнивает номер со знаком и без знака требуется компилятор преобразовать значение со знаком в числа без знака.  
  
 Чтобы устранить это предупреждение, приведении одного из двух типов при тестировании знаковых и беззнаковых типов.  
  
 Следующий пример приводит к возникновению ошибки C4018:  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```