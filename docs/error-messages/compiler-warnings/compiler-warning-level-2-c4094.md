---
title: Предупреждение компилятора (уровень 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c293522e5d60d0edb4cc2da289e0ece71f89329f
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052206"
---
# <a name="compiler-warning-level-2-c4094"></a>Предупреждение компилятора (уровень 2) C4094

без тега "token" не объявлен ни один символ

Компилятор обнаружил пустое объявление с использованием структуры, объединения или класса без тегов. Объявление игнорируется.

## <a name="example"></a>Пример

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Это условие приводит к ошибке в режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).