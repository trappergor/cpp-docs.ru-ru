---
title: Неустранимая ошибка ML A1008 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1008
dev_langs:
- C++
helpviewer_keywords:
- A1008
ms.assetid: fe592f9d-c37b-4cd8-a51d-e3c15ddcab83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec709823856e17c90d4af2a06262b30c966f39c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691942"
---
# <a name="ml-fatal-error-a1008"></a>Неустранимая ошибка ML A1008

**вложения непарные макросов**

Либо макрос не был завершен до достижения конца файла или директиву завершающий [ENDM](../../assembler/masm/endm.md) обнаружено вне блока макрос.

Одной из причин этой ошибки является пропуск точки перед [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md) или [. ХОТЯ](../../assembler/masm/dot-while.md).

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>