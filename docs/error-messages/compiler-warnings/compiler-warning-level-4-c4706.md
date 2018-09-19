---
title: Предупреждение компилятора (уровень 4) C4706 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 843edeaf490f27475003e9303f7929b818e2b104
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036960"
---
# <a name="compiler-warning-level-4-c4706"></a>Предупреждение компилятора (уровень 4) C4706

Назначение в пределах условного выражения

Тестовое значение в условном выражении появился в результате назначения.

Назначения имеет значение (значение в левой части назначения), которое может использоваться в другом, включая тестовое выражение.

Следующий пример приводит к возникновению ошибки C4706:

```
// C4706a.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a  = b ) // C4706
   {
   }
}
```

Предупреждение может возникнуть, даже если вы дважды скобки вокруг условия теста:

```
// C4706b.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a  =  b ) ) // C4706
   {
   }
}
```

Если нужно проверить отношение и для создания назначения, не используйте `==` оператор. Например, в следующей строке проверяется, является ли и b равны:

```
// C4706c.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a == b )
   {
   }
}
```

Если вы собираетесь значения результат назначения, проверьте, убедитесь, что назначение не нулевой или not null. Например следующий код не создает это предупреждение:

```
// C4706d.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a = b ) != 0 )
   {
   }
}
```