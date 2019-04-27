---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 23d34af470e825a8535de8cb28645a7bfb4c4d1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203101"
---
# <a name="externdef"></a>EXTERNDEF

Определяет один или несколько внешних переменных, меток или символов, которые называются *имя* типом `type`.

## <a name="syntax"></a>Синтаксис

> Тип: имени EXTERNDEF [[langtype]] [[, [[langtype]] Имя: type]]...

## <a name="remarks"></a>Примечания

Если *имя* определяется в модуле, он рассматривается как [ОТКРЫТЫЙ](../../assembler/masm/public-masm.md). Если *имя* на который приведена ссылка в модуле, он рассматривается как [EXTERN](../../assembler/masm/extern-masm.md). Если *имя* является ссылки нет, он игнорируется. `type` Может быть [ABS](../../assembler/masm/operator-abs.md), которая импортирует *имя* как константа. Обычно используется в включаемых файлов.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>