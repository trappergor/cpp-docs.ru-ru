---
title: Ошибка компилятора C2461 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39d58b315fdd7e3c4e1899041cebf8400813ed40
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029303"
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