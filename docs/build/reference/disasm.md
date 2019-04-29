---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 10e8187e896b3922438a8cf2dafa0aec4c91f904
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272065"
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

Только [/Headers](headers.md) параметр (программа DUMPBIN) доступен для использования на файлы, созданные [/GL (оптимизация всей программы)](gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
