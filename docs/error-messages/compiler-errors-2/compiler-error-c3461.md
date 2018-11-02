---
title: Ошибка компилятора C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: 81372c7a2468becf6dba3b30b62ee266eed272ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562920"
---
# <a name="compiler-error-c3461"></a>Ошибка компилятора C3461

"тип": только управляемый тип может быть перенаправлен

Перенаправление типа возможно только для типов среды CLR.  См. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) Дополнительные сведения.

Дополнительные сведения см. в разделе [Переадресация типа (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

```
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3461:

```
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```