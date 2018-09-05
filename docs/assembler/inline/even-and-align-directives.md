---
title: Директивы EVEN и ALIGN | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- align
- EVEN
dev_langs:
- C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06a1007c50e3490e5b14e4da886494557be0d37e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688305"
---
# <a name="even-and-align-directives"></a>Директивы EVEN и ALIGN

**Блок, относящийся только к системам Microsoft**

Несмотря на то, что встроенный ассемблер не поддерживает большинство директив MASM, он поддерживает `EVEN` и **ВЫРОВНЯТЬ**. Эти директивы помещают **NOP** (нет действия) инструкции в коде сборки, как нужно для выравнивания меток относительно определенных границ. В результате для некоторых процессоров операции поиска инструкций выполняются более эффективно.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>