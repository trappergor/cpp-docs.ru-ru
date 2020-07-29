---
title: Предупреждение компилятора (уровень 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: efe021c9994e20f2630e31537bcc6099783b4308
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220006"
---
# <a name="compiler-warning-level-4-c4062"></a>Предупреждение компилятора (уровень 4) C4062

> перечислитель "*идентификатор*" в операторе switch перечисления "*enumeration*" не обрабатывается

*Идентификатор* перечислителя не имеет связанного `case` обработчика в **`switch`** операторе, и отсутствует **`default`** Метка, которая может его перехватить. Отсутствующий вариант может быть ценным, а в коде возможной ошибкой. Связанное предупреждение об неиспользуемых перечислителях в **`switch`** инструкциях, имеющих **`default`** регистр, см. в разделе [C4061](compiler-warning-level-4-c4061.md).

Это предупреждение отключено по умолчанию. Дополнительные сведения о включении предупреждений, отключенных по умолчанию, см. [в разделе предупреждения компилятора, отключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4062 и демонстрирует, как это исправить:

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

## <a name="see-also"></a>См. также раздел

[Предупреждение компилятора (уровень 4) C4061](compiler-warning-level-4-c4061.md)
