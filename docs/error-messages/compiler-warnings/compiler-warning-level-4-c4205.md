---
title: Предупреждение компилятора (уровень 4) C4205 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4205
dev_langs:
- C++
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9847e3c009e132993bcbb6aa94d2064d61e40421
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042368"
---
# <a name="compiler-warning-level-4-c4205"></a>Предупреждение компилятора (уровень 4) C4205

использовано нестандартное расширение: объявление статической функции в области видимости функции

В расширениях Майкрософт (/Ze) **статический** функции могут быть объявлены внутри другой функции. Функция принимает глобальной области.

## <a name="example"></a>Пример

```
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

Подобная инициализация не допускается в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).