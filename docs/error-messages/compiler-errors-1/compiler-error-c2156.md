---
title: Ошибка компилятора C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: da8a5a9bcdeb33a9b308e24b129fded0595449a3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755906"
---
# <a name="compiler-error-c2156"></a>Ошибка компилятора C2156

директива pragma должна находиться вне функции

Директива pragma, которая должна быть определена на глобальном уровне (вне тела функции), находится внутри функции.

Следующий пример приводит к возникновению ошибки C2156:

```cpp
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```
