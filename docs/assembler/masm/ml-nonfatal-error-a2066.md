---
title: Некритичная ошибка ML A2066
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2066
helpviewer_keywords:
- A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
ms.openlocfilehash: 8dc3000b2edc2b1ecda7cc3952b554296de19aa3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855883"
---
# <a name="ml-nonfatal-error-a2066"></a>Некритичная ошибка ML A2066

**Несовместимый режим ЦП и размер сегмента**

Предпринята попытка открыть сегмент с атрибутом **USE16**, **USE32**или **Flat** , который не совместим с указанным ЦП, или перейти на 16-разрядный ЦП в 32-разрядном сегменте.

Атрибутам **USE32** и **Flat** должны предшествовать директивы процессора. 386 или более поздней версии.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>