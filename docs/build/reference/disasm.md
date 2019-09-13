---
title: /DISASM
ms.date: 01/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: fb394b2266470e77c50ce5398aea961c37ac34fb
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927725"
---
# <a name="disasm"></a>/DISASM

Распечатайте Дизассемблированный код разделов кода в выходных данных DUMPBIN.

## <a name="syntax"></a>Синтаксис

> **/DISASM** { **:** \[БАЙТОВВ|БАЙТАХ **]}**

### <a name="arguments"></a>Аргументы

**БАЙТ**<br/>
Включает байты инструкций вместе с интерпретируемыми кодом операций и аргументами в выходных данных дизассемблированного кода. Этот параметр используется по умолчанию.

**ЧИСЛО БАЙТОВ**<br/>
Не включает байты инструкций в выходных данных дизассемблированного кода.

## <a name="remarks"></a>Примечания

Параметр **/DISASM** отображает Дизассемблированный код разделов кода в файле. Он использует отладочные символы, если они есть в файле.

**/DISASM** следует использовать только в собственных, не управляемых изображениях. Эквивалентным средством для управляемого кода является [Ildasm](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Для использования в файлах, создаваемых параметром компилятора [/GL (оптимизация всей программы)](gl-whole-program-optimization.md) [, доступен только параметр DUMPBIN.](headers.md)

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
