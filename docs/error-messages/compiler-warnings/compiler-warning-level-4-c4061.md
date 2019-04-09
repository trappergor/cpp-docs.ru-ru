---
title: Предупреждение (уровень 4) C4061 компилятора
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 073e3e9cb1cb5bb6b0f66157c986072227960212
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237124"
---
# <a name="compiler-warning-level-4-c4061"></a>Предупреждение (уровень 4) C4061 компилятора

> Перечислитель "*идентификатор*«в параметре перечисления»*перечисления*" не обрабатывается явно меткой выбора

Заданный перечислитель *идентификатор* не имеет связанного обработчика `switch` оператору, у которого `default` случая. Отсутствует случай может быть случайно, или может оказаться проблемой. Он может зависеть от ли перечислитель обрабатывается в ситуации по умолчанию или нет. Связанные предупреждения на неиспользуемые перечислители в `switch` инструкции, которые не имеют `default` вариантов, см. в разделе [C4062](compiler-warning-level-4-c4062.md).

Это предупреждение отключено по умолчанию. Дополнительные сведения о том, как включить предупреждения, отключенные по умолчанию см. в разделе [компилятора предупреждения, Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4061; Добавьте запрос в службу отсутствует перечислитель для исправления:

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```

## <a name="see-also"></a>См. также

[Предупреждение компилятора (уровень 4) C4062](compiler-warning-level-4-c4062.md)
