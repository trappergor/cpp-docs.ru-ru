---
title: Ошибка компилятора C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: 3d290bd2288f76d0ddefa2057e3e01c9edc3cbc7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205326"
---
# <a name="compiler-error-c2461"></a>Ошибка компилятора C2461

> "*класс*": в синтаксисе конструктора отсутствуют формальные параметры

В конструкторе для класса не указаны формальные параметры. Объявление конструктора должно указывать список формальных параметров. Список может быть пустым.

Чтобы устранить эту проблему, добавьте пару круглых скобок после объявления класса *Class* *::*.*

## <a name="example"></a>Пример

В следующем примере показано, как исправить C2461:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```
