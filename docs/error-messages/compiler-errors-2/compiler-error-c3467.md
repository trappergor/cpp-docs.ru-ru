---
title: Ошибка компилятора C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: dd7046fcf87a6b8f095092ef0de4b94326151e87
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742831"
---
# <a name="compiler-error-c3467"></a>Ошибка компилятора C3467

"тип": данный тип уже был переадресован

Компилятор обнаружил несколько объявлений перенаправления типа для одного типа. Для каждого типа допускается только одно объявление.

Дополнительные сведения см. в разделе [Пересылка типов (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Примеры

В приведенном ниже примере создается компонент.

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

Следующий пример приводит к возникновению ошибки C3467:

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
