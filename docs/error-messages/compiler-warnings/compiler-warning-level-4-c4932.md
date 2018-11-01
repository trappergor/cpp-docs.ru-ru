---
title: Предупреждение компилятора (уровень 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: afeb27562c995bea38e9858c7ba3b279a98655cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515028"
---
# <a name="compiler-warning-level-4-c4932"></a>Предупреждение компилятора (уровень 4) C4932

__identifier(идентификатор) не и \__identifier(identifier) неразличимы.

Компилятору не удается различить **_finally** и `__finally` или `__try` и **_try** в качестве параметра, переданного [__identifier](../../windows/identifier-cpp-cli.md). Не следует пытаться использовать оба этих слова в качестве идентификаторов в одной и той же программе, так как это вызовет ошибку [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) .

Следующий пример приводит к возникновению предупреждения C4932:

```
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```