---
title: Встроенный сборщик
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
ms.openlocfilehash: 2050f59601755a93c73b743debacbf52ba9cec05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318078"
---
# <a name="inline-assembler"></a>Встроенный сборщик

**Microsoft Специфический**

Язык ассемблера может служить для целого ряда целей, например для повышения скорости работы программы, сокращения потребления памяти и управления оборудованием. Встроенный код на ассемблере можно использовать для внедрения инструкций языка ассемблера непосредственно в исходные программы С и С++ без дополнительных шагов по сборке и компоновке. Встроенный код на ассемблере встроен в компилятор, поэтому вам не требуется отдельный сборщик для языка ассемблера, такой как Microsoft Macro Assembler (MASM).

> [!NOTE]
> Программы со встроенным кодом на языке ассемблера не всегда можно перенести на другие аппаратные платформы. При разработке переносимой версии старайтесь не использовать встроенный код ассемблера.

Вличная сборка не поддерживается на процессорах ARM и x64.  В следующих разделах объясняется, как использовать встроенный код на ассемблере в программах Visual C/C++ для процессоров x86.

- [Обзор встроенного кода на ассемблере](../../assembler/inline/inline-assembler-overview.md)

- [Преимущества встроенного кода на ассемблере](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [Использование и сохранение регистров во встроенном коде на языке ассемблера](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [Переход к меткам во встроенном коде на языке ассемблера](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [Вызов C Функции в влинейной сборки](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [Вызов функций C++ во встроенном коде на языке ассемблера](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [Определение блоков __asm как макросов C](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [Оптимизация встроенного кода на языке ассемблера](../../assembler/inline/optimizing-inline-assembly.md)

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[Компилятор внутренностих и язык сборки](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[Языковая справка к СЗ](../../cpp/cpp-language-reference.md)<br/>
