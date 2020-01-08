---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: a74a5336e626f561f1fc61e866792ce193332d84
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316542"
---
# <a name="assume"></a>ASSUME

Включает проверку ошибок для значений регистров. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **Предположим**  *, сегрегистер* __:__ *Name* ⟦ __,__ *сегрегистер* __:__ *Name*... ⟧\
> **Предположим, что**  *регистр* __:__ *тип* ⟦ __,__ *регистр* __:__ *тип*... ⟧\
> **Считать**  *регистр* __: ошибка__ ⟦ __,__ *регистр* __: ошибка__... ⟧\
> **Предположим** , *⟦ регистр* __:__ ⟧**Nothing** ⟦ __,__ *Register* __: Nothing__... ⟧

## <a name="remarks"></a>Заметки

После вступления **в действие** , ассемблер следит за изменениями значений заданных регистров. При использовании **регистра возникает ошибка** . **Ничто не** удаляет проверку регистрации ошибок. В одной инструкции можно сочетать различные виды допущений.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
