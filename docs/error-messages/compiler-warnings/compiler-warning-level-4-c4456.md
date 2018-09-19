---
title: Предупреждение (уровень 4) C4456 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ab6939fe37260b906a43c4e2ff6683733348952
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039898"
---
# <a name="compiler-warning-level-4-c4456"></a>Компилятор предупреждение (уровень 4) C4456

> объявление "*идентификатор*" скрывает предыдущее локальное объявление

Объявление *идентификатор* в локальной области видимости скрывает объявление предыдущее локальное объявление с тем же именем. Это предупреждение позволяет узнать, что для ссылок *идентификатор* в локальной области, разрешены с использованием локально объявленным версии, не предыдущих local, который может или не может быть вашей целью. Чтобы устранить эту проблему, мы рекомендуем предоставить имена локальных переменных, которые не конфликтуют с других локальных имен.

## <a name="example"></a>Пример

В следующем примере возникает C4456, так как цикл управления переменной `int x` и локальной переменной `double x` в `member_fn` имеют те же имена. Чтобы устранить эту проблему, используйте разные имена локальных переменных.

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
