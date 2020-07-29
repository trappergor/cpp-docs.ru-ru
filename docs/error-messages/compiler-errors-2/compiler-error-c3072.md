---
title: Ошибка компилятора C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: bcf2548fbe1182f7f6c4bd966ca6aa9ef9f10089
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212609"
---
# <a name="compiler-error-c3072"></a>Ошибка компилятора C3072

> оператор "*operator-Name*" не может применяться к экземпляру класса ссылки

для преобразования экземпляра ссылочного класса в тип Handle используется унарный оператор *Name-operator*

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
