---
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 18cb6e563084e8c5357bec2a8052a2b38fcdffee
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317556"
---
# <a name="savereg"></a>.SAVEREG

Создает `UWOP_SAVE_NONVOL` или `UWOP_SAVE_NONVOL_FAR` запись кода очистки для указанного регистра (*reg*) и смещения (*смещения*) с использованием текущего смещения пролога. MASM выберет наиболее эффективную кодировку.

## <a name="syntax"></a>Синтаксис

> **. Саверег** *reg* __,__ *смещение*

## <a name="remarks"></a>Заметки

**. САВЕРЕГ** позволяет пользователям ml64. exe указывать, как кадрировать функцию Frame, и допускается только в прологе, который расширяется из объявления кадра [процесса](proc.md) в [. ](dot-endprolog.md)Директива ендпролог. Эти директивы не создают код. они создают только `.xdata` и `.pdata`. **. САВЕРЕГ** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
