---
title: Некритичная ошибка ML A2219
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: 61fa6bc6d630f1e8a8ac84492b60690c9545fb3e
ms.sourcegitcommit: 79e985d3c6e8ccaf94f6e641972887cae8c6eeb0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2019
ms.locfileid: "66197682"
---
# <a name="ml-nonfatal-error-a2219"></a>Некритичная ошибка ML A2219

> Неправильное выравнивание для смещения в код очистки

## <a name="remarks"></a>Примечания

Операнд для [ &period;ALLOCSTACK](../../assembler/masm/dot-allocstack.md) и [ &period;SAVEREG](../../assembler/masm/dot-savereg.md) должно быть кратным 8.  Операнд для [ &period;SAVEXMM128](../../assembler/masm/dot-savexmm128.md) и [ &period;SETFRAME](../../assembler/masm/dot-setframe.md) должен быть кратен 16.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)
