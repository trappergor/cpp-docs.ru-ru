---
title: Ошибка компилятора C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 1e53a0c08f07bf69378fbb7603f63c596f641355
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758662"
---
# <a name="compiler-error-c2524"></a>Ошибка компилятора C2524

"деструктор": деструктор или метод завершения должен иметь список параметров "void"

Деструктор или метод завершения имел список параметров, который не является [void](../../cpp/void-cpp.md). Другие типы параметров не допускаются.

## <a name="example"></a>Пример

Следующий код воспроизводит C2524.

```cpp
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

## <a name="example"></a>Пример

Следующий код воспроизводит C2524.

```cpp
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```
