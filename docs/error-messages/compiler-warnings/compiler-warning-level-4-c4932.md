---
title: Предупреждение компилятора (уровень 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: cd37ee67545918991b286d16d0fe27b47414b3c3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769827"
---
# <a name="compiler-warning-level-4-c4932"></a>Предупреждение компилятора (уровень 4) C4932

__identifier(идентификатор) не и \__identifier(identifier) неразличимы.

Компилятору не удается различить **_finally** и `__finally` или `__try` и **_try** в качестве параметра, переданного [__identifier](../../extensions/identifier-cpp-cli.md). Не следует пытаться использовать оба этих слова в качестве идентификаторов в одной и той же программе, так как это вызовет ошибку [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) .

Следующий пример приводит к возникновению предупреждения C4932:

```
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```