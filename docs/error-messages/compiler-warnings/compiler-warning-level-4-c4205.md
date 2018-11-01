---
title: Предупреждение компилятора (уровень 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: 1b165d2bdb2fb50df89fdd77c734c054a40b6e95
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622486"
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