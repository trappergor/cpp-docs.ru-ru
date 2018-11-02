---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 77f6f05029ec4480afb2180eab0bb57838d643a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462950"
---
# <a name="disasm"></a>/DISASM

Печать результатов дизассемблирования разделов кода, в выходных данных (программа DUMPBIN).

## <a name="syntax"></a>Синтаксис

> **/ DISASM**{**:**\[**БАЙТ**|**NOBYTES**]}

### <a name="arguments"></a>Аргументы

**БАЙТ**<br/>
Включает байты инструкции вместе с интерпретируемым коды операций и аргументы в выходных данных Дизассемблированный код. Этот параметр используется по умолчанию.

**NOBYTES**<br/>
Не поддерживает инструкции байты в выходных данных Дизассемблированный код.

## <a name="remarks"></a>Примечания

**/DISASM** отображает Дизассемблированный код секций кода в файле. Отладочные символы используются в том случае, если они присутствуют в файле.

**/ DISASM** следует использовать только в машинном коде, не управляемых образов. Аналогичный инструмент для управляемого кода является [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования на файлы, созданные [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)
