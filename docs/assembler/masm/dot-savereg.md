---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: cac7aa7f2bdbf6b60831d2beb062f86559ec0358
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472828"
---
# <a name="savereg"></a>.SAVEREG

Создает либо `UWOP_SAVE_NONVOL` или `UWOP_SAVE_NONVOL_FAR` очистки запись для указанного регистра (`reg`) и смещения (`offset`) с помощью текущего смещения пролога. MASM выберет наиболее эффективную кодировку.

## <a name="syntax"></a>Синтаксис

> . Смещение SAVEREG reg

## <a name="remarks"></a>Примечания

. SAVEREG позволяет пользователю указать, каким образом функция кадра освобождает ml64.exe и разрешен только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директива. Эти директивы не создают код; они создают только `.xdata` и `.pdata`. . SAVEREG должно предшествовать инструкции, которые на деле реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе для обеспечения соглашения.

Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>