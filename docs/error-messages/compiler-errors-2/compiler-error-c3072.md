---
title: Ошибка компилятора C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: a8fe0802a7529551fce1c0b7242c867db52d8842
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756764"
---
# <a name="compiler-error-c3072"></a>Ошибка компилятора C3072

оператор "operator" не может применяться к экземпляру класса ссылки

Используйте унарный оператор "`operator`" для преобразования экземпляра ссылочного класса в тип Handle

Для типа CLR требуются операторы CLR, а не машинные (или стандартные) операторы.  Дополнительные сведения см. в разделе [Отслеживание ссылочного оператора](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3072.

```cpp
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```
