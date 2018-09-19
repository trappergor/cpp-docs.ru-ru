---
title: Предупреждение компилятора (уровень 4) C4238 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4d5f358d08f81e6b8097140ad47d54f4b3b3fed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057032"
---
# <a name="compiler-warning-level-4-c4238"></a>Предупреждение компилятора (уровень 4) C4238

использовано нестандартное расширение: правостороннего значения класса в качестве левостороннего значения

Для совместимости с предыдущими версиями Visual c++, расширения Microsoft (**/Ze**) можно будет использовать тип класса, как rvalue в контексте, который явно или неявно принимает его адрес. В некоторых случаях, как показано в примере ниже это может быть опасно.

## <a name="example"></a>Пример

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

Такое использование вызывает ошибку совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).