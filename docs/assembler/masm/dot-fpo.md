---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: b793b3efa72a676b800c10b98ea06001ddcf10d5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491436"
---
# <a name="fpo"></a>.FPO

Тот. Директива FPO управляет эмиссией отладочных записей в сегмент. Debug $ F или раздел.

## <a name="syntax"></a>Синтаксис

> FPO (*кдвлокалс*, *кдвпарамс*, *кбпролог*, *кбрегс*, *фусебп*, *кбфраме*)

### <a name="parameters"></a>Параметры

*кдвлокалс*<br/>
Число локальных переменных — Неподписанное 32 разрядное значение.

*кдвпарамс*<br/>
Размер параметров в DWORD, 16 разрядных значений без знака.

*cbProlog*<br/>
Число байтов в коде пролога функции — 8 разрядное значение без знака.

*кбрегс*<br/>
Число сохраняемых регистров.

*фусебп*<br/>
Указывает, выделен ли регистр EBP. значение 0 или 1.

*кбфраме*<br/>
Указывает тип кадра.  Дополнительные сведения см. в разделе [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
