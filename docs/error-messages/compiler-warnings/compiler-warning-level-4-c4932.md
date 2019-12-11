---
title: Предупреждение компилятора (уровень 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: dd1db3cccf9f1b24f82ddddf10fcf35f39a9251a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988788"
---
# <a name="compiler-warning-level-4-c4932"></a>Предупреждение компилятора (уровень 4) C4932

__identifier (идентификатор) и \__identifier (идентификатор) неразличимы

Компилятору не удается различить **_finally** и `__finally` или `__try` и **_try** в качестве параметра, переданного [__identifier](../../extensions/identifier-cpp-cli.md). Не следует пытаться использовать оба этих слова в качестве идентификаторов в одной и той же программе, так как это вызовет ошибку [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) .

Следующий пример приводит к возникновению предупреждения C4932:

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
