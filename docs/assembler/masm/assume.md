---
title: ПРЕДПОЛОЖИМ | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ASSUME
dev_langs:
- C++
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0e43548292d2ffecbebdaead6aa12d6dacc352
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693812"
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