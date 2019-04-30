---
title: Ошибка компилятора C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 5f9b60499fd3c3bd5f06834e3c4f6482031066d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406968"
---
# <a name="compiler-error-c2823"></a>Ошибка компилятора C2823

> шаблон typedef не допускается

Шаблоны не допускаются в `typedef` определений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2823 и показан один из способов ее устранения:

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```