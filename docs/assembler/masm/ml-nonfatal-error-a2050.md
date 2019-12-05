---
title: Некритичная ошибка ML A2050
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 15c6449ff4207c92dee28120d4f61be641cf01c8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856581"
---
# <a name="ml-nonfatal-error-a2050"></a>Некритичная ошибка ML A2050

**число Real или BCD не разрешено**

В качестве инициализатора данных использовалось числовое значение с плавающей запятой (вещественное число) или константа с двоичной кодировкой (BCD).

Произошла одна из следующих ошибок:

- В выражении использовалось вещественное число или BCD.

- Вещественное число было использовано для инициализации директивы, отличной от [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md)или [тбите](../../assembler/masm/tbyte.md).

- Для инициализации директивы, отличной от `TBYTE`, использовался BCD.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>