---
title: Ошибка компилятора C3156
ms.date: 11/04/2016
f1_keywords:
- C3156
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
ms.openlocfilehash: 115e8cd63562964b19e4a67f7a649ecfab2596c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465264"
---
# <a name="compiler-error-c3156"></a>Ошибка компилятора C3156

class: нельзя иметь локальное определение управляемого типа или типа WinRT

Функция не может содержать определение или объявление управляемого класса, структуры или интерфейса либо класса, структуры или интерфейса WinRT.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3156.

```
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
