---
title: Ошибка компилятора C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: 70375950543b9525fca10fff3084c923095fa35e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173491"
---
# <a name="compiler-error-c3467"></a>Ошибка компилятора C3467

"тип": данный тип уже был переадресован

Компилятор обнаружил несколько объявлений перенаправления типа для одного типа. Для каждого типа допускается только одно объявление.

Дополнительные сведения см. в разделе [Переадресация типа (C++выполняет)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

```
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3467:

```
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```