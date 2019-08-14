---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3bdb6af98aa71fef3d4af24091dc7463d917ce15
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915964"
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
Указывает тип кадра.  Дополнительные сведения см. в разделе [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
