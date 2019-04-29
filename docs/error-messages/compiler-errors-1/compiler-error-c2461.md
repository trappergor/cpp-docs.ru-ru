---
title: Ошибка компилятора C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: e8f82ed4ce8ad77a22961a42c8e9a256e6f647db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368036"
---
# <a name="compiler-error-c2461"></a>Ошибка компилятора C2461

> "*класс*": отсутствие формальные параметры в синтаксисе конструктора

Конструктор для класса не содержит формальные параметры. В объявлении конструктора необходимо указать список формальных параметров. Список может быть пустым.

Чтобы устранить эту проблему, добавьте пару скобок после объявления *класс*:: **класс*.

## <a name="example"></a>Пример

В следующем примере показано возникновение C2461:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```