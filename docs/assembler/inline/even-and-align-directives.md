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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167323"
---
# <a name="even-and-align-directives"></a>Директивы EVEN и ALIGN

**Блок, относящийся только к системам Microsoft**

Несмотря на то, что встроенный ассемблер не поддерживает большинство директив MASM, он поддерживает `EVEN` и **ВЫРОВНЯТЬ**. Эти директивы помещают **NOP** (нет действия) инструкции в коде сборки, как нужно для выравнивания меток относительно определенных границ. В результате для некоторых процессоров операции поиска инструкций выполняются более эффективно.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>