---
title: Ошибка компилятора C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: 6f60a9abbc5702c1a0d14d0f894c9b1684378c3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759364"
---
# <a name="compiler-error-c3238"></a>Ошибка компилятора C3238

"тип": тип с этим именем уже перенаправлен в сборку "сборка"

В клиентском приложении был определен тип, который также определен посредством синтаксиса перенаправления в связанной сборке. Нельзя определять оба типа в области приложения.

Дополнительные сведения см. в разделе [Переадресация типов (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) .

## <a name="example"></a>Пример

В следующем примере создается сборка, содержащая тип, перенаправленный из другой сборки.

```cpp
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Пример

В следующем примере создается сборка, которая используется для содержания определения типа, но содержит не только синтаксис перенаправления для типа.

```cpp
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3238.

```cpp
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```
