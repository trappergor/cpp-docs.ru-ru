---
title: Ошибка компилятора C3466
ms.date: 11/04/2016
f1_keywords:
- C3466
helpviewer_keywords:
- C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
ms.openlocfilehash: 6eae1c44d8dae9118258c83c5919947803f49215
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402559"
---
# <a name="compiler-error-c3466"></a>Ошибка компилятора C3466

«Тип»: специализацию универсального класса переадресовывать невозможно

Нельзя использовать перенаправление на специализацию универсального класса типов.

Дополнительные сведения см. в разделе [Переадресация типа (C++выполняет)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

```
// C3466.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3466:

```
// C3466_b.cpp
// compile with: /clr /c
#using "C3466.dll"
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```