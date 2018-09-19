---
title: Предупреждение (уровень 4) C4458 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 873aa94db899ae6620e2bbb1f24277c6e7c841c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094550"
---
# <a name="compiler-warning-level-4-c4458"></a>Компилятор предупреждение (уровень 4) C4458

> объявление "*идентификатор*" скрывает член класса

Объявление *идентификатор* в локальной области видимости скрывает объявление с идентичными именами *идентификатор* в области видимости класса. Это предупреждение позволяет узнать, что для ссылок *идентификатор* в этой области, разрешения в локально объявленным версии, а не класс члена версию, что может не соответствовать намерениям. Чтобы устранить эту проблему, мы рекомендуем предоставить имена локальных переменных, которые не конфликтуют с именами член класса.

## <a name="example"></a>Пример

В следующем примере возникает C4458, так как параметр `x` и локальной переменной `y` в `member_fn` имеют те же имена, что данные-члены в классе. Чтобы устранить эту проблему, используйте разные имена для параметров и локальных переменных.

```cpp
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;
        // To fix this issue, change the parameter name x
        // and local name y to something that does not
        // conflict with the data member names.
    }
} s;
```
