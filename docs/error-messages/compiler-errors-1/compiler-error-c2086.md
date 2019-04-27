---
title: Ошибка компилятора C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 094a794627b886abc7db5ba4d74c6fe97ff82461
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216130"
---
# <a name="compiler-error-c2086"></a>Ошибка компилятора C2086

«Идентификатор»: переопределение

Идентификатор определен более одного раза или следующее объявление отличается от предыдущего.

C2086 также может быть результатом инкрементное построение сборки C#. Перестройте сборки C#, чтобы устранить эту ошибку.

Следующий пример приводит к возникновению ошибки C2086:

```
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```