---
title: .PUSHFRAME
description: Описывает. Директива MASM PUSHFRAME, используемая для указания способа очистки функции Frame.
ms.date: 12/06/2019
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 5f951396291ecb12dab500a364f176106c5daa8b
ms.sourcegitcommit: 2cac0150ab3bc8260f866451019b8e22c7e1ac11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "74945856"
---
# <a name="pushframe"></a>.PUSHFRAME

Создает `UWOP_PUSH_MACHFRAME` запись кода очистки. Если указано необязательное ключевое слово **Code** , то элементу кода очистки присваивается модификатор 1. В противном случае модификатор равен 0.

## <a name="syntax"></a>Синтаксис

> **. PUSHFRAME** ⟦**Code**⟧;;

## <a name="remarks"></a>Заметки

. PUSHFRAME позволяет пользователям ml64. exe указать, как функция Frame-Wind очищается. Это допускается только в прологе, который расширяется из объявления кадра [процесса](../../assembler/masm/proc.md) в [. ](../../assembler/masm/dot-endprolog.md)Директива ендпролог. Эти директивы не создают код; они создают только `.xdata` и `.pdata`. **. PUSHFRAME** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
