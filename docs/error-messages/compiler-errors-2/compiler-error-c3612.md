---
title: Ошибка компилятора C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: a6084632ac0a84cc058ea73eb3c2b632208792eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475937"
---
# <a name="compiler-error-c3612"></a>Ошибка компилятора C3612

«Тип»: запечатанный класс не может быть абстрактным

Типы, определенные с помощью `value` являются запечатанными по умолчанию, и класс является абстрактным, если он реализует все методы базового. Запечатанный абстрактный класс не может быть базовым классом и не может создавать его экземпляр.

Дополнительные сведения см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3612:

```
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```