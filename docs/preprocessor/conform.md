---
title: Прагма conform
ms.date: 08/29/2019
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: 816ff85bb19f549c6ea072073bd89fcd503545f2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220496"
---
# <a name="conform-pragma"></a>Прагма conform

**C++Зависящ**

Задает поведение во время выполнения параметра компилятора [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) .

## <a name="syntax"></a>Синтаксис

> **#pragma соответствует (** *имя* [ **, показать** ] [ **,** { **On** | **Off** }] [[ **,** { **Push** | **POP** }] [ **,** *идентификатор* [ **,** { **On** **Off}** ]  |  ] ] **)**

### <a name="parameters"></a>Параметры

*безымян*\
Определяет имя параметра компилятора, которое требуется изменить. Единственное допустимое *имя* : `forScope`.

**казывающи**\
Используемых Приводит к тому, что текущее значение параметра *Name* (true или false) будет отображаться с помощью предупреждающего сообщения во время компиляции. Например, `#pragma conform(forScope, show)`.

**вкл**., **выкл** .\
Используемых Для параметра *Name* в значение **On** включается параметр компилятора [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) . Значение по умолчанию — **Off**.

**распространение**\
Используемых Помещает текущее значение *имени* во внутренний стек компилятора. При указании *идентификатора*можно указать значение **On** или **Off** , чтобы *имя* было отправлено в стек. Например, `#pragma conform(forScope, push, myname, on)`.

**Рор**\
Используемых Задает значение *Name* в начале внутреннего стека компилятора, а затем извлекает стек. Если идентификатор указан с помощью **POP**, стек будет извлечен до тех пор, пока не найдет запись с *идентификатором*, которая также будет извлечена. Текущее значение *имени* в следующей записи в стеке станет новым значением для *Name*. Если указать **POP** с идентификатором , который не находится в записи в стеке, то **POP** игнорируется.

*Идентификатор*\
Используемых Можно добавить с помощью команды **Push** или **POP** . Если используется *идентификатор* , можно также использовать спецификатор **On** или **Off** .

## <a name="example"></a>Пример

```cpp
// pragma_directive_conform.cpp
// compile with: /W1
// C4811 expected
#pragma conform(forScope, show)
#pragma conform(forScope, push, x, on)
#pragma conform(forScope, push, x1, off)
#pragma conform(forScope, push, x2, off)
#pragma conform(forScope, push, x3, off)
#pragma conform(forScope, show)
#pragma conform(forScope, pop, x1)
#pragma conform(forScope, show)

int main() {}
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
