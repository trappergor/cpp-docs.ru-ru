---
title: Предупреждение (уровень 4) C4457 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62232a814bed47f8b6a5041d20e6f37776abffe8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093536"
---
# <a name="compiler-warning-level-4-c4457"></a>Компилятор предупреждение (уровень 4) C4457

> объявление "*идентификатор*" скрывает параметр функции

Объявление *идентификатор* в локальной области видимости скрывает объявление параметра функции с одинаковыми именами. Это предупреждение позволяет узнать, что для ссылок *идентификатор* в локальной области решения локально объявленным версию, а не параметр, который может или не может быть вашей целью. Чтобы устранить эту проблему, мы рекомендуем предоставить имена локальных переменных, которые не конфликтуют с именами параметров.

## <a name="example"></a>Пример

В следующем примере возникает C4457, так как параметр `x` и локальной переменной `x` в `member_fn` имеют те же имена. Чтобы устранить эту проблему, используйте разные имена для параметров и локальных переменных.

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
