---
title: / DISASM | Документы Microsoft
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
ms.openlocfilehash: 89b0784ff10e7d9521351e01d8907c963c9304fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="disasm"></a>/DISASM

Печать Дизассемблирование разделов кода в выводе DUMPBIN.

## <a name="syntax"></a>Синтаксис

> **/ DISASM**{**:**\[**БАЙТ**|**NOBYTES**]}  

### <a name="arguments"></a>Аргументы

**БАЙТ**  
Содержится в байтах инструкция вместе с интерпретируемых коды операций и аргументы вывода Дизассемблированный код. Этот параметр используется по умолчанию.

**NOBYTES**  
Не включает инструкции байты в выходных данных Дизассемблированный код.

## <a name="remarks"></a>Примечания

**/DISASM** параметр отображает Дизассемблирование разделов кода в файле. Он использует символы отладки, если они присутствуют в файле.

**/ DISASM** следует использовать только в машинном коде, не управляемых образов. Средство эквивалент для управляемого кода — [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования на файлы, созданные [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)  
