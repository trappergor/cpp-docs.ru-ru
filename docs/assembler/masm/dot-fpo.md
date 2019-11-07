---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3938d9194c35d567ea670e0b92a731193ccd2254
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703800"
---
# <a name="fpo-32-bit-masm"></a>. FPO (32-разрядный MASM)

Тот. Директива FPO управляет эмиссией отладочных записей в сегмент. Debug $ F или раздел. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> FPO (*кдвлокалс*, *кдвпарамс*, *кбпролог*, *кбрегс*, *фусебп*, *кбфраме*)

### <a name="parameters"></a>Параметры

*кдвлокалс*<br/>
Число локальных переменных — Неподписанное 32 разрядное значение.

*кдвпарамс*<br/>
Размер параметров в DWORD, 16 разрядных значений без знака.

*кбпролог*<br/>
Число байтов в коде пролога функции — 8 разрядное значение без знака.

*кбрегс*<br/>
Число сохраняемых регистров.

*фусебп*<br/>
Указывает, выделен ли регистр EBP. значение 0 или 1.

*кбфраме*<br/>
Указывает тип кадра.  Дополнительные сведения см. в разделе [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
