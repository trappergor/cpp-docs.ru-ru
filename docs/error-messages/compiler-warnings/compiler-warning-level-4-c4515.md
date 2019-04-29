---
title: Предупреждение компилятора (уровень 4) C4515
ms.date: 11/04/2016
f1_keywords:
- C4515
helpviewer_keywords:
- C4515
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
ms.openlocfilehash: 147855f607d8ca72aa32548bf817484b6c0c3cfe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395304"
---
# <a name="compiler-warning-level-4-c4515"></a>Предупреждение компилятора (уровень 4) C4515

«namespace»: пространство имен обращается к самому себе

Пространство имен — используется рекурсивно.

Следующий пример приводит к возникновению ошибки C4515:

```
// C4515.cpp
// compile with: /W4
namespace A
{
   using namespace A; // C4515
}

int main()
{
}
```