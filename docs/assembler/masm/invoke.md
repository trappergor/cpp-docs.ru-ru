---
title: ВЫЗВАТЬ | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e5698acf9986903a1d6d731c1047484a0ce6904
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676521"
---
# <a name="invoke"></a>INVOKE

Вызывает процедуру по адресу, заданному по *выражение*, передачи аргументов в стеке или в регистрах, в соответствии с стандартные соглашения о вызовах типа языка.

## <a name="syntax"></a>Синтаксис

> INVOKE *выражение* [[, *аргументы*]]

## <a name="remarks"></a>Примечания

Все аргументы, переданные в процедуру может быть выражением, паре регистров или выражение адреса (предшествует выражение `ADDR`).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>