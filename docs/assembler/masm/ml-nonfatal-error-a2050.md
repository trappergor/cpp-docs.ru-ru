---
title: Некритичная ошибка ML A2050
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 59d08b9c2743a3b45633527bcc54b3e1c4d6a58c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177556"
---
# <a name="ml-nonfatal-error-a2050"></a>Некритичная ошибка ML A2050

**реальный или BCD номер не разрешен**

Число с плавающей запятой (real) или константа двоично-десятичный (BCD) использовался отличное от как инициализатор данных.

Одной из следующих причин:

- Вещественное число или данных конфигурации загрузки был использован в выражении.

- Вещественное число, использовавшийся для инициализации директиву, отличное от [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), или [TBYTE](../../assembler/masm/tbyte.md).

- BCD, использовавшийся для инициализации директиву, отличное от `TBYTE`.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>