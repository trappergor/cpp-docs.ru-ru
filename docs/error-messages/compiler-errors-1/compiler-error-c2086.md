---
title: Ошибка компилятора C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 417763e8c26918d3cd83702b283244d1c13d9d1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735753"
---
# <a name="compiler-error-c2086"></a>Ошибка компилятора C2086

"идентификатор": переопределение

Идентификатор определен более одного раза, или последующее объявление отличается от предыдущего.

C2086 также может быть результатом инкрементного создания сборки, на которую C# указывает ссылка. Чтобы устранить C# эту ошибку, перестройте сборку.

Следующий пример приводит к возникновению ошибки C2086:

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
