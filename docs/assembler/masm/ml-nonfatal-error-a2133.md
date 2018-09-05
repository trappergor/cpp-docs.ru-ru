---
title: Некритичная ошибка ML A2133 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0df094f5e7135ffb3b9a5f09383e03e411755de3
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678070"
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133

**значение, перезаписываются INVOKE регистра**

Регистр был передан в качестве аргумента в процедуру, но код, созданный путем [INVOKE](../../assembler/masm/invoke.md) передавать другие аргументы уничтожения содержимое регистра.

Регистры AX, AL, AH, EAX, DX, список Рассылки, Диффи-Хелмана и EDX может использоваться ассемблер, для выполнения преобразования данных.

Используйте другой регистр.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>