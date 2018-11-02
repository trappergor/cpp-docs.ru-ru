---
title: Ошибка компилятора C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 06d4c19208bd242169e1cd07a71e8a568f46f7b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466096"
---
# <a name="compiler-error-c2383"></a>Ошибка компилятора C2383

"*символ*": аргументы по умолчанию не разрешены для этого символа

Компилятор C++ не поддерживает аргументы по умолчанию в указателях на функции.

Этот код был принят компилятором Visual C++ в версиях до Visual Studio 2005, но теперь выдает ошибку. Для кода, который работает во всех версиях Visual C++ не назначайте значение по умолчанию аргумент указателя на функцию.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2383 и показано возможное решение:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```