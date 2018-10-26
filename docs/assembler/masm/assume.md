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
ms.openlocfilehash: 6fbba50e56ae06dc3afb64582d4a131bba75a6c8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055857"
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