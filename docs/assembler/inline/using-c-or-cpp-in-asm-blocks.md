---
title: Использование C или C++ в блоках __asm
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, mixing instructions with C/C++ statements
- symbols, in __asm blocks
- macros, __asm blocks
- preprocessor directives, used in __asm blocks
- type names, used in __asm blocks
- preprocessor directives
- preprocessor, directives
- constants, in __asm blocks
- comments, in __asm blocks
- typedef names, used in __asm blocks
- __asm keyword [C++], C/C++ elements in
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
ms.openlocfilehash: 16b298b92a4ba40d9091499a1821ad4f3c413d6c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854528"
---
# <a name="using-c-or-c-in-__asm-blocks"></a>Использование C или C++ в блоках __asm

**Блок, относящийся только к системам Майкрософт**

Поскольку инструкции встроенного кода на языке ассемблера можно комбинировать с операторами C или C++, они могут ссылаться на переменные C или C++ по имени и использовать множество других элементов этих языков.

Блок `__asm` может использовать следующие элементы языка.

- Символы, включая метки и имена переменных и функций.

- Константы, включая символьные константы и члены `enum`.

- Макросы и директивы препроцессора.

- Комментарии ( __/\* \*/__ и __//__ )

- Имена типов (если тип MASM допустим).

- `typedef` имена, обычно используемые с такими операторами, как **ptr** и **Type** , или для указания структуры или членов объединения.

В блоке `__asm` можно указать целочисленные константы с помощью нотации C или нотации основания системы счисления ассемблера (например, 0x100 и 100h эквивалентны). Это позволяет определить (с помощью `#define`) константу в C, а затем использовать ее в C и C++, а также частях сборки программы. Можно также указать константы в восьмеричной системе счисления, поместив перед ними 0. Например, 0777 указывает восьмеричную константу.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Использование операторов в блоках __asm](../../assembler/inline/using-operators-in-asm-blocks.md)

- [Использование блоков C C++ или Symbols_in __asm](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [Доступ к данным C или C++ в блоках __asm](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Написание функций во встроенном коде на языке ассемблера](../../assembler/inline/writing-functions-with-inline-assembly.md)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>
