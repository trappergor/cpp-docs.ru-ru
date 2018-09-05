---
title: Некритичная ошибка ML A2006 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2006
dev_langs:
- C++
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f287c6ab46c6af71ba6dc0032f332ce3cc489454
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677409"
---
# <a name="ml-nonfatal-error-a2006"></a>Некритичная ошибка ML A2006

**Неопределенный символ: идентификатор**

Была предпринята попытка использовать символ, который не был определен.

Мог произойти одно из следующих:

- Символ не определен.

- Поле не является членом указанной структуры.

- Символ был определен во включаемом файле, который не был включен.

- Внешний символ был использован без [EXTERN](../../assembler/masm/extern-masm.md) или [EXTERNDEF](../../assembler/masm/externdef.md) директива.

- Было неправильно указано имя символа.

- Ссылка на метку локальный код за пределами его области.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>