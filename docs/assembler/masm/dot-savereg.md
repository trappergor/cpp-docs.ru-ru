---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 324cf0e70a7ad619e5741c9acc18c24a72f54d13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397969"
---
# <a name="savereg"></a>.SAVEREG

Создает `UWOP_SAVE_NONVOL` или `UWOP_SAVE_NONVOL_FAR` запись кода очистки для указанного регистра (*reg*) и смещения (*смещения*) с использованием текущего смещения пролога. MASM выберет наиболее эффективную кодировку.

## <a name="syntax"></a>Синтаксис

> **. Саверег** *reg* __,__ *смещение*

## <a name="remarks"></a>Примечания

**. САВЕРЕГ**позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и допускается только в прологе, который расширяется из объявления кадра [процесса](../../assembler/masm/proc.md) в [. ](../../assembler/masm/dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. САВЕРЕГ** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
