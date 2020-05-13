---
title: Предупреждение компилятора (уровень 2) C4308
ms.date: 11/04/2016
f1_keywords:
- C4308
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
ms.openlocfilehash: 138344be8d70866583214a9c5a26f10c972a7889
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161846"
---
# <a name="compiler-warning-level-2-c4308"></a>Предупреждение компилятора (уровень 2) C4308

отрицательная целая константа преобразована в тип без знака

Выражение преобразует отрицательную целочисленную константу в тип без знака. Результат выражения, вероятно, не имеет смысла.

## <a name="example"></a>Пример

```cpp
// C4308.cpp
// compile with: /W2
unsigned int u = (-5 + 3U);   // C4308

int main()
{
}
```
