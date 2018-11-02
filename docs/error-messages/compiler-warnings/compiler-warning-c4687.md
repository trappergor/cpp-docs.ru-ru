---
title: Предупреждение компилятора C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 50551faf817f83d8a4af848a75af67ebe7004fe7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635487"
---
# <a name="compiler-warning-c4687"></a>Предупреждение компилятора C4687

«класс»: Запечатанный абстрактный класс не может реализовывать интерфейс «интерфейс»

Запечатанный абстрактный тип обычно содержит только для хранения статических функций-членов.

Дополнительные сведения см. в разделе [абстрактный](../../windows/abstract-cpp-component-extensions.md)и [запечатанный](../../windows/sealed-cpp-component-extensions.md).

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