---
title: Предупреждение компилятора (уровень 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 18c5a51e24af36c5a330e10a66ce3dcc38295fb1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225284"
---
# <a name="compiler-warning-level-4-c4061"></a>Предупреждение компилятора (уровень 4) C4061

> перечислитель "*идентификатор*" в операторе switch enum "*enumeration*" не обрабатывается явно меткой Case

Указанный *идентификатор* перечислителя не имеет связанного обработчика в **`switch`** операторе, который имеет **`default`** регистр. Отсутствующий вариант может быть ценным или непроблемой. Он может зависеть от того, обрабатывается ли перечислитель по умолчанию или нет. Связанное предупреждение об использовании неиспользуемых перечислителей в **`switch`** инструкциях без **`default`** регистра см. в разделе [C4062](compiler-warning-level-4-c4062.md).

Это предупреждение отключено по умолчанию. Дополнительные сведения о включении предупреждений, отключенных по умолчанию, см. [в разделе предупреждения компилятора, отключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4061; Добавьте случай для отсутствующего перечислителя, чтобы исправить следующее:

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

## <a name="see-also"></a>См. также статью

[Предупреждение компилятора (уровень 4) C4062](compiler-warning-level-4-c4062.md)
