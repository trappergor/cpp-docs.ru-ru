---
title: / DISASM | Документация Майкрософт
ms.date: 1/17/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /disasm
dev_langs:
- C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5a4d930c47d2a3c2808cbd0a343c5c68de4ac9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707191"
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
