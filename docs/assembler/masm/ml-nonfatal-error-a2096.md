---
title: Некритичная ошибка ML A2096 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f4ef76dca10b1208a931bc3e1cc09d82a639d2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679602"
---
# <a name="ml-nonfatal-error-a2096"></a>Некритичная ошибка ML A2096

**Сегмент, группы или ожидается регистр**

Сегмент или группы ожидался, но не найден.

Одной из следующих причин:

- Левый операнд, указанный с сегментом переопределить оператор (**:**) не сегмент register (CS, DS, SS, ES, FS или GS), имя группы, имя сегмента или выражение сегмента.

- [Предположим, ЧТО](../../assembler/masm/assume.md) директива передан регистр без адрес допустимый сегмент, регистр, группы или специальную **НЕСТРУКТУРИРОВАННЫЙ** группы.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>