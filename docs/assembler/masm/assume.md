---
title: ASSUME
ms.date: 08/30/2018
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 97a57cc8a1acccf70572ff963e496aa79fa3ab43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166468"
---
# <a name="assume"></a>ASSUME

Включает проверку значений регистров.

## <a name="syntax"></a>Синтаксис

> Предположим, ЧТО *segregister*:*имя* [[, *segregister*:*имя*]]...<br/>
> Предположим, ЧТО *dataregister*:*тип* [[, *dataregister*:*тип*]]...<br/>
> Предположим, ЧТО *зарегистрировать*: ошибка [[, *зарегистрировать*: ошибка]]...<br/>
> Предположим, ЧТО [[*зарегистрировать*:]] NOTHING [[, *зарегистрировать*: ничего не]]...

## <a name="remarks"></a>Примечания

После `ASSUME` изменения вступают в силу, ассемблер отслеживает изменения значений заданного регистров. **Ошибка** приводит к ошибке, если используется регистр. **Ничего не** удаляет зарегистрировать проверки на наличие ошибок. Вы можете объединить различные виды предположения в одной инструкции.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>