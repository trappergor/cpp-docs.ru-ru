---
title: . SAVEXMM128 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d44855d3449000c588f7e840753bd734af4b1af
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689911"
---
# <a name="savexmm128"></a>.SAVEXMM128

Создает либо `UWOP_SAVE_XMM128` или `UWOP_SAVE_XMM128_FAR` очистки запись для указанного регистра XMM и смещение, с помощью текущего смещения пролога. MASM выберет наиболее эффективную кодировку.

## <a name="syntax"></a>Синтаксис

> .savexmm128 xmmreg, смещение

## <a name="remarks"></a>Примечания

. SAVEXMM128 позволяет ml64.exe пользователю указать, каким образом функция кадра освобождает и разрешен только в пределах пролога, начиная с позиции [PROC](../../assembler/masm/proc.md) объявление КАДРА [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) директива. Эти директивы не создают код; они создают только `.xdata` и `.pdata`. . SAVEXMM128 должно предшествовать инструкции, которые на деле реализуют действия, чтобы быть развернут. Рекомендуется переносить директивы очистки и код, который они предназначены для очистки в макросе для обеспечения соглашения.

*Смещение* должен быть кратен 16.

Дополнительные сведения см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>