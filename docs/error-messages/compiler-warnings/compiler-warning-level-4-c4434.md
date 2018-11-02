---
title: Предупреждение компилятора (уровень 4) C4434
ms.date: 11/04/2016
f1_keywords:
- C4434
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
ms.openlocfilehash: 6a7d760a7d192c7e0a7bd5e16f77efe1a4099c31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591269"
---
# <a name="compiler-warning-level-4-c4434"></a>Предупреждение компилятора (уровень 4) C4434

конструктор класса должен иметь режим доступа private; закрытый доступ

C4434 указывает, что компилятор изменил доступность статический конструктор. Статические конструкторы должны быть закрытыми, так как они предназначены только для вызова среда CLR. Дополнительные сведения см. в разделе [статические конструкторы](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4434.

```
// C4434.cpp
// compile with: /W4 /c /clr
public ref struct R {
   static R(){}   // C4434
};
```