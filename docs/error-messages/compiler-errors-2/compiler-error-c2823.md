---
title: Ошибка компилятора C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: ef07e1b542c4c3977f35de7ed9cd0f0a5358cedb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201959"
---
# <a name="compiler-error-c2823"></a>Ошибка компилятора C2823

> Недопустимый шаблон typedef

Шаблоны не допускаются в определениях `typedef`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2823 и демонстрирует один из способов его исправления:

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```
