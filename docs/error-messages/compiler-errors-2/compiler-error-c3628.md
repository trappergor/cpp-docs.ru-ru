---
title: Ошибка компилятора C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 9976cb2425f8f855ffb2903c07de22822c781e20
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755828"
---
# <a name="compiler-error-c3628"></a>Ошибка компилятора C3628

"базовый класс": Managed или Винртклассес поддерживают только открытое наследование

Предпринята попытка использовать класс Managed или WinRT в качестве [закрытого](../../cpp/private-cpp.md) или [защищенного](../../cpp/protected-cpp.md) базового класса. Класс Managed или WinRT можно использовать только в качестве базового класса с [открытым](../../cpp/public-cpp.md) доступом.

В следующем примере показано возникновение ошибки C3628 и приводятся сведения по ее устранению.

```cpp
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
