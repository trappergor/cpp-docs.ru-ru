---
title: Предупреждение компилятора (уровень 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: 1ce32ef4d07ea5e2c6f328578837f805eed5c897
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408138"
---
# <a name="compiler-warning-level-4-c4670"></a>Предупреждение компилятора (уровень 4) C4670

"идентификатор": этот базовый класс недоступен

Указанный базовый класс объекта, который необходимо создать в блоке **try** , недоступен. Если объект возник, то его экземпляры создавать нельзя. Обратите внимание, что базовый класс наследуется вместе с правильным спецификатором доступа.

Следующий пример приводит к возникновению предупреждения C4670:

```
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