---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 17edea122afc03a8c3a2fdc86ee6c06c2ccf3c85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398490"
---
# <a name="dosseg-32-bit-masm"></a>. ДОССЕГ (32-разрядный компилятор MASM)

Упорядочивает сегменты в соответствии с соглашением о сегментах MS-DOS: сначала код, затем сегменты не в ДГРАУП, а затем сегменты в ДГРАУП. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **.DOSSEG**

## <a name="remarks"></a>Примечания

Сегменты в ДГРАУП следуют в следующем порядке: сегменты не в BSS или стек, затем сегменты BSS и, наконец, сегменты СТЕКа. В основном используется для обеспечения поддержки Информация CodeView в изолированных программах MASM. То же, что и [доссег](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
