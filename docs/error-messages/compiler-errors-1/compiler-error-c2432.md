---
title: Ошибка компилятора C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: d4234626bc246d6da87be68b03d44562dd5990ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744515"
---
# <a name="compiler-error-c2432"></a>Ошибка компилятора C2432

Недопустимая ссылка на 16-разрядные данные в "identifier"

16-разрядный регистр используется в качестве индекса или базового регистра. Компилятор не поддерживает ссылки на 16-разрядные данные. 16-разрядные регистры не могут использоваться в качестве индексов или базовых регистров при компиляции для 32-разрядного кода.

Следующий пример приводит к возникновению ошибки C2432:

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
