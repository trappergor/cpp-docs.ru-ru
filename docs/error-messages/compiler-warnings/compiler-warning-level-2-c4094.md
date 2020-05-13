---
title: Предупреждение компилятора (уровень 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c90ad202e193f21955d396dd2aff6b39d3a968c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174340"
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
