---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 4bf8f0c41e9ce3e296cf201efd4fd9be2033cbdb
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73702466"
---
# <a name="assume-32-bit-masm"></a>ПРЕДПОЛАГАЕТся (32-разрядный MASM)

Включает проверку ошибок для значений регистров. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> ПРЕДПОЛОЖИМ, *сегрегистер*:*Name* [[, *сегрегистер*:*имя*]]...<br/>
> Допустим *регистр*:*тип* [[, *регистр*:*тип*]]...<br/>
> СЧИТАТЬ *регистр*: ошибка [[, *регистр*: Ошибка]]...<br/>
> ПРЕДПОЛОЖИМ [[*регистр*:]] Nothing [[, *Register*: Nothing]]...

## <a name="remarks"></a>Заметки

После вступления `ASSUME` в действие ассемблер следит за изменениями значений заданных регистров. При использовании **регистра возникает ошибка** . **Ничто не** удаляет проверку регистрации ошибок. В одной инструкции можно сочетать различные виды допущений.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>