---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 83d6e81ea7dd35038f27f2721f3cc41fe49ef1bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570515"
---
# <a name="fpo"></a>.FPO

. Директива FPO контролирует вывод записи об отладке .debug$ F сегмента или раздел.

## <a name="syntax"></a>Синтаксис

> FPO (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*,  *cbFrame*)

### <a name="parameters"></a>Параметры

*cdwLocals*<br/>
Количество локальных переменных, значение без знака 32-разрядная версия.

*cdwParams*<br/>
Размер параметров в ЧЕТЫРЕХБАЙТОВЫЙ, значение без знака 16-разрядных систем.

*cbProlog*<br/>
Число байтов в кода пролога функции значение 8-разрядное число без знака.

*cbRegs*<br/>
Номер сохраненные регистры.

*fUseBP*<br/>
Указывает, выделен ли регистр EBP. 0 или 1.

*cbFrame*<br/>
Указывает тип пакета.  См. в разделе [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data) Дополнительные сведения.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>