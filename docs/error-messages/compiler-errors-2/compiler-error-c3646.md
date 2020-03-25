---
title: Ошибка компилятора C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 13a3ebeb6e7783687abc73cd0dcc018abe827809
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200477"
---
# <a name="compiler-error-c3646"></a>Ошибка компилятора C3646

> "спецификатор": Неизвестный спецификатор переопределения

## <a name="remarks"></a>Remarks

Компилятор обнаружил маркер в том месте, где ожидалось найти спецификатор переопределения, но маркер не был распознан компилятором.

Например, если нераспознанный *спецификатор* является **_NOEXCEPT**, замените его ключевым словом, **Кроме**.

Дополнительные сведения см. в разделе [Описатели переопределения](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3646 и демонстрирует способ исправления:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```
