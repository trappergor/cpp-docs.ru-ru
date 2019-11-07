---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 8f0388c3df9804c0cdb105162a962a44fe207345
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703309"
---
# <a name="dosseg-32-bit-masm"></a>. ДОССЕГ (32-разрядный компилятор MASM)

Упорядочивает сегменты в соответствии с соглашением о сегментах MS-DOS: сначала код, затем сегменты не в ДГРАУП, а затем сегменты в ДГРАУП. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> .DOSSEG

## <a name="remarks"></a>Заметки

Сегменты в ДГРАУП следуют в следующем порядке: сегменты не в BSS или стек, затем сегменты BSS и, наконец, сегменты СТЕКа. В основном используется для обеспечения поддержки Информация CodeView в изолированных программах MASM. То же, что и [доссег](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>