---
title: Предупреждение компилятора (уровень 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: e0582f3dfdd223b4571e361dc69fae1990aeea1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498219"
---
# <a name="compiler-warning-level-4-c4242"></a>Предупреждение компилятора (уровень 4) C4242

«Идентификатор»: преобразование из «тип1» в «тип2», возможна потеря данных

Типы являются разными. Преобразование типа может привести к потере данных. Преобразование типа выполняется компилятором.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Дополнительные сведения об ошибке C4242 см. в разделе [типичные ошибки компилятора](/windows/desktop/WinProg64/common-compiler-errors).

Следующий пример приводит к возникновению ошибки C4242:

```
// C4242.cpp
// compile with: /W4
#pragma warning(4:4242)
int func() {
   return 0;
}

int main() {
   char a;
   a = func();   // C4242, return type and variable type do not match
}
```