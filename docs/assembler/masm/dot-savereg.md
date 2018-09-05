---
title: . SAVEREG | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEREG
dev_langs:
- C++
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7010664cd2e80841d9e35d8fcf72d195cecf796
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688993"
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