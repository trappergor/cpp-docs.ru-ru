---
title: Ошибка компилятора C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 3025dbf7c6bf4701218c2d9a956cae26d7180848
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757609"
---
# <a name="compiler-error-c3279"></a>Ошибка компилятора C3279

Частичные и явные специализации, а также явные создания экземпляров шаблонов классов, объявленные в пространстве имен CLI, запрещены

Пространство имен `cli` определено Майкрософт и содержит псевдошаблоны. В компиляторе Майкрософт C++ не разрешены пользовательские, частичные и явные специализации, а также явное создание экземпляров шаблонов классов в этом пространстве имен.

При компиляции следующего примера возникнет ошибка C3279:

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
