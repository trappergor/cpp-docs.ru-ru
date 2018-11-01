---
title: Предупреждение компилятора (уровень 1) C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: 988c1fcbe0826582dceaa527811c688711fd8906
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428048"
---
# <a name="compiler-warning-level-1-c4160"></a>Предупреждение компилятора (уровень 1) C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>Директива pragma (pop,...): не найден ранее занесенный в стек идентификатор "*идентификатор*"

## <a name="remarks"></a>Примечания

Оператор pragma в исходном коде пытается извлечь из стека идентификатор, который не был занесен в стек. Чтобы устранить это предупреждение, необходимо убедиться в том, что идентификатор, извлекаемый из стека, был туда соответствующим образом занесен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4160 и показаны способы ее устранения:

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```