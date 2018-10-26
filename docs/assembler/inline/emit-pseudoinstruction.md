---
title: псевдоинструкция _emit | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 569e3a078109e66df7dcf5cbf314817ce0786899
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061930"
---
# <a name="emit-pseudoinstruction"></a>Псевдоинструкция _emit

**Блок, относящийся только к системам Microsoft**

**_Emit** pseudoinstruction определяет один байт в текущем положении в текущем сегменте текста. **_Emit** отчасти похожа [DB](../../assembler/masm/db.md) директивы MASM.

В следующем примере в код помещаются байты 0x4A, 0x43 и 0x4B:

```cpp
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B
.
.
.
__asm {
    randasm
    }
```

> [!CAUTION]
> Если псевдокоманда `_emit` создает инструкции, которые изменяют регистры, а приложение компилируется с включенными оптимизациями, то компилятор не в состоянии определить, на какие регистры она действует. Например если `_emit` создает инструкцию, которая изменяет **rax** регистр, компилятор не знает, **rax** был изменен. Затем компилятор может сделать неверное допущение о значении этого регистра после выполнения встроенного кода на языке ассемблера. Поэтому запущенное приложение может работать непредсказуемым образом.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>