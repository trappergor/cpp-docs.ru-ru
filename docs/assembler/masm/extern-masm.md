---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 30d1b3ae7c6676aeb97b91c7627da859525b9ce1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497361"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Определяет один или несколько внешних переменных, меток или символов, которые называются *имя* типом *тип*.

## <a name="syntax"></a>Синтаксис

> EXTERN [[*langtype*]] *имя* [[(*altid*)]]: *тип* [[, [[*langtype*]]  *имя* [[(*altid*)]]: *тип*]]...

## <a name="remarks"></a>Примечания

*Тип* может быть [ABS](../../assembler/masm/operator-abs.md), которая импортирует *имя* как константа. Совпадение с кодом [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>