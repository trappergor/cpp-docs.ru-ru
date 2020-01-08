---
title: Некритичная ошибка ML A2050
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 311aedd0cc739fd862efb0a18cc444b3fb75b165
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316984"
---
# <a name="ml-nonfatal-error-a2050"></a>Некритичная ошибка ML A2050

**число Real или BCD не разрешено**

В качестве инициализатора данных использовалось числовое значение с плавающей запятой (вещественное число) или константа с двоичной кодировкой (BCD).

Произошла одна из следующих ошибок:

- В выражении использовалось вещественное число или BCD.

- Вещественное число было использовано для инициализации директивы, отличной от [DWORD](dword.md), [QWORD](qword.md)или [тбите](tbyte.md).

- Для инициализации директивы, отличной от `TBYTE`, использовался BCD.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
