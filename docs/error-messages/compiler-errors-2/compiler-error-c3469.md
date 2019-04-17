---
title: Ошибка компилятора C3469
ms.date: 11/04/2016
f1_keywords:
- C3469
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
ms.openlocfilehash: 1e935fb90c93d6f301226f3e9029c04929f179ac
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773285"
---
# <a name="compiler-error-c3469"></a>Ошибка компилятора C3469

"тип": универсальный класс переадресовывать невозможно

Перенаправление типов неприменимо к универсальному классу.

Дополнительные сведения см. в разделе [Переадресация типа (C++выполняет)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

```
// C3469.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3466:

```
// C3469_b.cpp
// compile with: /clr /c
#using "C3469.dll"
[assembly:TypeForwardedTo(GR::typeid)];   // C3469
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```