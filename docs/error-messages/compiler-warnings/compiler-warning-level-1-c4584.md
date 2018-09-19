---
title: Предупреждение компилятора (уровень 1) C4584 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9db97bf35034f7ca628f860924bfb9a1fccc942f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036258"
---
# <a name="compiler-warning-level-1-c4584"></a>Предупреждение компилятора (уровень 1) C4584

«класс1»: базового класса «класс2» уже является базовым классом для «class3»

Класса, который вы определили наследует из двух классов, один из которых наследуется от другого. Пример:

```
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

В этом случае будет выдано предупреждение для класса C, так как он наследуется из класса A и класса B, который наследует от класса а. Это предупреждение служит в качестве напоминания, что необходимо указывать полное использование членов базового класса, или создается ошибка компилятора из-за неоднозначности, обратитесь к члену класса.