---
title: .PUSHFRAME
description: Описывает. Директива MASM PUSHFRAME, используемая для указания способа очистки функции Frame.
ms.date: 12/06/2019
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 0aaec119d26d87fddb1eba505458da1250a5926e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317582"
---
# <a name="pushframe"></a>.PUSHFRAME

Создает `UWOP_PUSH_MACHFRAME` запись кода очистки. Если указано необязательное ключевое слово **Code** , то элементу кода очистки присваивается модификатор 1. В противном случае модификатор равен 0.

## <a name="syntax"></a>Синтаксис

> **. PUSHFRAME** ⟦**Code**⟧;;

## <a name="remarks"></a>Заметки

. PUSHFRAME позволяет пользователям ml64. exe указать, как функция Frame-Wind очищается. Это допускается только в прологе, который расширяется из объявления кадра [процесса](proc.md) в [. ](dot-endprolog.md)Директива ендпролог. Эти директивы не создают код; они создают только `.xdata` и `.pdata`. **. PUSHFRAME** должен предшествовать инструкциям, которые фактически реализуют действия, которые должны быть развернуты. Рекомендуется заключить в оболочку как директивы очистки, так и код, предназначенный для очистки макроса, чтобы обеспечить соблюдение соглашения.

Дополнительные сведения см. в статье [MASM для x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
