---
title: Предупреждение компилятора C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 1978e1a35ba5b5d59b5961a21378d8af6921d145
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776318"
---
# <a name="compiler-warning-c4687"></a>Предупреждение компилятора C4687

«класс»: Запечатанный абстрактный класс не может реализовывать интерфейс «интерфейс»

Запечатанный абстрактный тип обычно содержит только для хранения статических функций-членов.

Дополнительные сведения см. в разделе [абстрактный](../../extensions/abstract-cpp-component-extensions.md)и [запечатанный](../../extensions/sealed-cpp-component-extensions.md).

C4687 выдается как ошибка по умолчанию. Вы можете отключить C4687 с [предупреждение](../../preprocessor/warning.md) директивы pragma. Если вы уверены, что вы хотите реализовать интерфейс в Запечатанный абстрактный тип, можно отключить C4687.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4687.

```
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```