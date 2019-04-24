---
title: Предупреждение компилятора (уровень 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: 79658afc31565b708cdbd8a88f49b887cdd10cf3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59237189"
---
# <a name="compiler-warning-level-4-c4062"></a>Предупреждение компилятора (уровень 4) C4062

> Перечислитель "*идентификатор*«в параметре перечисления»*перечисления*" не обрабатывается

Перечислитель *идентификатор* не имеет связанного `case` обработчик в `switch` инструкции и не `default` метка, которую можно перехватить. Отсутствует случай может быть случайно и потенциальные ошибки в коде. Связанные предупреждения на неиспользуемые перечислители в `switch` инструкций, которые `default` вариантов, см. в разделе [C4061](compiler-warning-level-4-c4061.md).

Это предупреждение отключено по умолчанию. Дополнительные сведения о том, как включить предупреждения, отключенные по умолчанию см. в разделе [компилятора предупреждения, Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4062 и показаны способы ее устранения:

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>См. также

[Предупреждение компилятора (уровень 4) C4061](compiler-warning-level-4-c4061.md)
