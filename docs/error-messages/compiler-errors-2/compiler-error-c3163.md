---
title: Ошибка компилятора C3163 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7be8fbba29cf82070d6fd96c76f810bda961489
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250893"
---
# <a name="compiler-error-c3163"></a>Ошибка компилятора C3163
«конструктор»: атрибуты несовместимы с предыдущим объявлением  
  
 Один или несколько атрибутов, которые применяются к определению, конфликтуют с атрибутами, которые применяются к объявлению.  
  
 Один из способов устранения ошибки C3163 — атрибутов из опережающего объявления. Все атрибуты для опережающего объявления должна быть меньше, чем атрибуты в определении или не более равны им.  
  
 Возможная причина ошибки C3163 включает в себя язык заметки исходного кода Microsoft (SAL). Макросы SAL не расширяться, если при компиляции проекта с помощью **/ analyze** флаг. Программа, которая компилируется без ошибок без / analyze может создавать ошибку C3163 при попытке повторной компиляции с помощью параметра / analyze. Дополнительные сведения о языке SAL см. в разделе [заметки SAL](../../c-runtime-library/sal-annotations.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3163.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## <a name="see-also"></a>См. также  
 [Заметки SAL](../../c-runtime-library/sal-annotations.md)