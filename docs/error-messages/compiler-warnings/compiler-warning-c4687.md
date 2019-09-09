---
title: Предупреждение компилятора C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 83f5c535f9cf252783110838c181c88c8b0096ee
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631607"
---
# <a name="compiler-warning-c4687"></a>Предупреждение компилятора C4687

> "*класс*": запечатанный абстрактный класс не может реализовать интерфейс "*интерфейс*"

## <a name="remarks"></a>Примечания

Запечатанный абстрактный тип обычно полезен только для хранения статических функций-членов.

Дополнительные сведения см. в разделе [абстрактные](../../extensions/abstract-cpp-component-extensions.md) и [запечатанные](../../extensions/sealed-cpp-component-extensions.md).

По умолчанию C4687 выдается как ошибка. C4687 можно отключить с помощью директивы pragma [warning](../../preprocessor/warning.md) . Если вы уверены, что необходимо реализовать интерфейс в запечатанном абстрактном типе, можно отключить C4687.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4687.

```cpp
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```
