---
title: Компилятор предупреждение (уровень 1) C4079
ms.date: 11/04/2016
f1_keywords:
- C4079
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
ms.openlocfilehash: 8f9a9e05ab2a65ad954f9928f7b9fab0e7fee9cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564571"
---
# <a name="compiler-warning-level-1-c4079"></a>Компилятор предупреждение (уровень 1) C4079

непредвиденный токен "токен"

Непредвиденная лексема-разделитель из списка аргументов директивы pragma. В оставшейся части директива pragma была пропущена.

Следующий пример приводит к возникновению ошибки C4079:

```
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```