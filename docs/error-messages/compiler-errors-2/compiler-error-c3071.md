---
title: Ошибка компилятора C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: 6960dbf62fd30b822f0d7c7a3c46a29a4115913f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428357"
---
# <a name="compiler-error-c3071"></a>Ошибка компилятора C3071

оператор "operator" можно применить только к экземпляру класса ref или к типу значений

Оператор среды CLR нельзя использовать с неуправляемым типом. Оператор можно использовать в классе или структуре ссылки (тип значения), но не в управляемом типе, таком как int, или псевдониме управляемого типа, таком как System::Int32. Эти типы не могут быть упакованы в коде C++ так, чтобы они ссылались на управляемую переменную, поэтому оператор нельзя использовать.

Дополнительные сведения см. в разделе [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3071.

```
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```