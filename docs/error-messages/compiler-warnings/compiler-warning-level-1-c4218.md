---
title: Предупреждение компилятора (уровень 4) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: f7553b30a17f50f559351353552fd656fceb8657
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199801"
---
# <a name="compiler-warning-level-1-c4218"></a>Предупреждение компилятора (уровень 4) C4218

использовано нестандартное расширение: необходимо указать по крайней мере класс хранения или тип

Используя расширения Майкрософт по умолчанию (/Ze), можно объявить переменную без указания типа или класса хранения. Тип по умолчанию —`int`.

## <a name="example"></a>Пример

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Такие объявления недопустимы в режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
