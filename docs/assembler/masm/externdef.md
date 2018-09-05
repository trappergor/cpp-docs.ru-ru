---
title: EXTERNDEF | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5c3d42cabb88c38ce1d98da24cd2cb4ddec8d5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683665"
---
# <a name="externdef"></a>EXTERNDEF

Определяет один или несколько внешних переменных, меток или символов, которые называются *имя* типом `type`.

## <a name="syntax"></a>Синтаксис

> Тип: имени EXTERNDEF [[langtype]] [[, [[langtype]] Имя: type]]...

## <a name="remarks"></a>Примечания

Если *имя* определяется в модуле, он рассматривается как [ОТКРЫТЫЙ](../../assembler/masm/public-masm.md). Если *имя* на который приведена ссылка в модуле, он рассматривается как [EXTERN](../../assembler/masm/extern-masm.md). Если *имя* является ссылки нет, он игнорируется. `type` Может быть [ABS](../../assembler/masm/operator-abs.md), которая импортирует *имя* как константа. Обычно используется в включаемых файлов.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>