---
title: соответствует | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05b1f9fef458b8c21de9eb3942730ff901d3922e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071236"
---
# <a name="conform"></a>conform
**Конкретных C++**

Задает поведение времени выполнения [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) параметр компилятора.

## <a name="syntax"></a>Синтаксис

> **#pragma соответствовать (** *имя* [**, Показать** ] [**,** { **на** | **off** }] [[**,** { **принудительной** | **pop** }] [**,** *идентификатор* ]] **)**

### <a name="parameters"></a>Параметры

*name*<br/>
Определяет имя параметра компилятора, которое требуется изменить. Единственным допустимым *имя* является `forScope`.

**Показать**<br/>
(Необязательно) Вызывает текущий параметр *имя* (true или false), для отображения посредством предупреждения во время компиляции. Например, `#pragma conform(forScope, show)`.

**на**, **off**<br/>
(Необязательно) Установка *имя* для **на** позволяет [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) параметр компилятора. По умолчанию используется **off**.

**push**<br/>
(Необязательно) Помещает текущее значение *имя* на внутренний стек компилятора. Если указать *идентификатор*, можно указать **на** или **off** значение *имя* помещается в стек. Например, `#pragma conform(forScope, push, myname, on)`.

**pop**<br/>
(Необязательно) Задает значение *имя* значение вверху внутреннего стека компилятора, а затем точки присутствия стека. Если идентификатор определен с помощью **pop**, стек будет извлекаться обратно, пока не будет найдена запись с *идентификатор*, который также будет извлечен; текущее значение для *имя* в следующей записи в стеке становится новым значением для *имя*. Если указать **pop** с *идентификатор* , не является записью в стеке, **pop** учитывается.

*identifier*<br/>
(Необязательно) Можно включить с помощью **принудительной** или **pop** команды. Если *идентификатор* используется, а затем **на** или **off** также можно использовать описатель.

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

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)