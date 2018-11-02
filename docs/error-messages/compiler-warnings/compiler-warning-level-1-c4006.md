---
title: Предупреждение компилятора (уровень 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: 97f50bdf4454a284953bd70e83574f5d0a86d1e3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571500"
---
# <a name="compiler-warning-level-1-c4006"></a>Предупреждение компилятора (уровень 1) C4006

\#undef ожидается идентификатор

Директива `#undef` не указывает идентификатор для отмены. Директива игнорируется. Чтобы устранить это предупреждение, не забудьте указать идентификатор. Следующий пример приводит к возникновению ошибки C4006.

```
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```