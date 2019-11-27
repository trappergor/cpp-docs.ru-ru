---
title: Предупреждение компилятора (уровень 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: f1db3eabc3b614019676dc4494e83104c62fe579
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627310"
---
# <a name="compiler-warning-level-1-c4218"></a>Предупреждение компилятора (уровень 1) C4218

использовано нестандартное расширение: необходимо указать по крайней мере класс хранения или тип

Используя расширения Майкрософт по умолчанию (/Ze), можно объявить переменную без указания типа или класса хранения. Значение по умолчанию — `int`.

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