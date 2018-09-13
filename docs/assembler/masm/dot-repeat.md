---
title: . ПОВТОРИТЕ | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .REPEAT
dev_langs:
- C++
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8856ed0e1d86277a413baac2c56e5c5ca2ea9ff0
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "43687956"
---
# <a name="repeat"></a>.REPEAT

Создает код, который повторяет выполнение блока *инструкций* пока `condition` становится истинным. [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md), который принимает значение true, если CX равен нулю, может заменить [. ПОКА](../../assembler/masm/dot-until.md). `condition` Является необязательным при использовании **. UNTILCXZ**.

## <a name="syntax"></a>Синтаксис

> .REPEAT<br/>
> операторы<br/>
> . Вплоть до условия

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>