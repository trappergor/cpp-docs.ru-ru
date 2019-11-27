---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 08bc5ab50e15aa59e0c49992d1810c7de20f364e
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397954"
---
# <a name="savexmm128"></a>.SAVEXMM128

Создает `UWOP_SAVE_XMM128` или `UWOP_SAVE_XMM128_FAR` запись кода очистки для указанного регистра XMM и смещения с использованием текущего смещения пролога. MASM выберет наиболее эффективную кодировку.

## <a name="syntax"></a>Синтаксис

> **. SAVEXMM128** *ксммрег* , *смещение*

## <a name="remarks"></a>Примечания

**. SAVEXMM128** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и может использоваться только в прологе, который расширяется из объявления кадра [процесса](../../assembler/masm/proc.md) в [. ](../../assembler/masm/dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. . SAVEXMM128 должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

*смещение* должно быть кратным 16.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
