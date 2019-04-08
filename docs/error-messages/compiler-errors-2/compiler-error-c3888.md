---
title: Ошибка компилятора C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: e4d52946126e7be6c6f2aef34b5eb5a93a0babad
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033645"
---
# <a name="compiler-error-c3888"></a>Ошибка компилятора C3888

"имя": выражение константы, связанное с этими данными-членом литерала, не поддерживается в C++/CLI

Член данных *имя* , объявленный с помощью ключевого слова [literal](../../extensions/literal-cpp-component-extensions.md) , инициализирован со значением, не поддерживаемым компилятором. Компилятор поддерживает только целочисленные константы, перечисления и строковые типы. Возможной причиной ошибки **C3888** может быть то, что член данных инициализирован с помощью байтового массива.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Проверьте, имеет ли объявленный член данных литерала поддерживаемый тип.

## <a name="see-also"></a>См. также

[литерал](../../extensions/literal-cpp-component-extensions.md)