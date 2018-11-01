---
title: Компилятор предупреждение (уровень 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: b2406357baf70e45566f2d2f25839d151bac4186
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484877"
---
# <a name="compiler-warning-level-1-c4144"></a>Компилятор предупреждение (уровень 1) C4144

«выражение»: выражение отношения в качестве выражения для выбора вариантов

Заданного реляционного выражения использовался в качестве выражения управления [переключения](../../cpp/switch-statement-cpp.md) инструкции. Связанные операторы case будет предложен логические значения. Следующий пример приводит к возникновению ошибки C4144:

```
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```