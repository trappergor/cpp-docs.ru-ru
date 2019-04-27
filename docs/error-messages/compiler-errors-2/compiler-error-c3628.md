---
title: Ошибка компилятора C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 581aae7e1f979b3dd39caf2ce3d263fdb856c56a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221689"
---
# <a name="compiler-error-c3628"></a>Ошибка компилятора C3628

«базовый класс»: управляемый или WinRTclasses поддерживают только открытое наследование

Была предпринята попытка использовать управляемый или WinRT классов как [частного](../../cpp/private-cpp.md) или [защищенные](../../cpp/protected-cpp.md) базового класса. Управляемого массива или класса WinRT может использоваться только как базовый класс с [открытый](../../cpp/public-cpp.md) доступа.

В следующем примере показано возникновение ошибки C3628 и приводятся сведения по ее устранению.

```
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
