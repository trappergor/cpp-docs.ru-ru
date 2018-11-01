---
title: Директивы EVEN и ALIGN
ms.date: 08/30/2018
f1_keywords:
- align
- EVEN
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
ms.openlocfilehash: 522d5689d680d0fc334743d2802abe21570dd6f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604385"
---
# <a name="even-and-align-directives"></a>Директивы EVEN и ALIGN

**Блок, относящийся только к системам Microsoft**

Несмотря на то, что встроенный ассемблер не поддерживает большинство директив MASM, он поддерживает `EVEN` и **ВЫРОВНЯТЬ**. Эти директивы помещают **NOP** (нет действия) инструкции в коде сборки, как нужно для выравнивания меток относительно определенных границ. В результате для некоторых процессоров операции поиска инструкций выполняются более эффективно.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>