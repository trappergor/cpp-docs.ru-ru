---
title: Предупреждение компилятора (уровень 4) C4213 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4213
dev_langs:
- C++
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59bb2d8b2c25516558c4810d190f0bec9b98c086
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025624"
---
# <a name="compiler-warning-level-4-c4213"></a>Предупреждение компилятора (уровень 4) C4213

использовано нестандартное расширение: приведение типов для левостороннего значения

В расширениях Майкрософт по умолчанию (/Ze) можно использовать приведения в левой части оператора присваивания.

## <a name="example"></a>Пример

```
// C4213.c
// compile with: /W4
void *a;
void f()
{
   int   i[3];
   a = &i;
   *(( int * )a )++ = 3;  // C4213
}

int main()
{
}
```

Такого приведения являются недопустимыми в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).