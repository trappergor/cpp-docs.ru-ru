---
title: Некритичная ошибка ML A2050 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd2e0e6c2fc818ef9286fd303c07a26bdd8b4e5a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680675"
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