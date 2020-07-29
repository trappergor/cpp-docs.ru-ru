---
title: Предупреждение компилятора (уровень 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: 15f0b249d9e91c0ebcc5655b5edffbd2d8cafa93
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230614"
---
# <a name="compiler-warning-level-4-c4670"></a>Предупреждение компилятора (уровень 4) C4670

"идентификатор": этот базовый класс недоступен

Указанный базовый класс объекта, который должен быть создан в **`try`** блоке, недоступен. Если объект возник, то его экземпляры создавать нельзя. Обратите внимание, что базовый класс наследуется вместе с правильным спецификатором доступа.

Следующий пример приводит к возникновению предупреждения C4670:

```cpp
// C4670.cpp
// compile with: /EHsc /W4
class A
{
};

class B : /* public */ A
{
} b;   // inherits A with private access by default

int main()
{
    try
    {
       throw b;   // C4670
    }
    catch( B )
    {
    }
}
```
