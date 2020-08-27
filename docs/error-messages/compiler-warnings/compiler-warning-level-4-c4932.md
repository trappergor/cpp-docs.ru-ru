---
title: Предупреждение компилятора (уровень 4) C4932
description: Описывает предупреждение компилятора Microsoft C/C++ C4932.
ms.date: 08/25/2020
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: ece2ae14fd8e1198a97f5e772fcce52c47464878
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898297"
---
# <a name="compiler-warning-level-4-c4932"></a>Предупреждение компилятора (уровень 4) C4932

> `__identifier(identifier_1)` и `__identifier(identifier_2)` являются неразличимыми

Компилятору не удается различить **`_finally`** Параметры и **`__finally`** или **`__try`** и **`_try`** в качестве параметра, передаваемого в [`__identifier`](../../extensions/identifier-cpp-cli.md) . Не следует пытаться использовать оба этих слова в качестве идентификаторов в одной и той же программе, так как это вызовет ошибку [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) .

Следующий пример приводит к возникновению предупреждения C4932:

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
