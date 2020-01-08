---
title: Некритичная ошибка ML A2066
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2066
helpviewer_keywords:
- A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
ms.openlocfilehash: 4c7c32264fe5daa6cd4e14f47cff111899e8f8d6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316893"
---
# <a name="ml-nonfatal-error-a2066"></a>Некритичная ошибка ML A2066

**Несовместимый режим ЦП и размер сегмента**

Предпринята попытка открыть сегмент с атрибутом **USE16**, **USE32**или **Flat** , который не совместим с указанным ЦП, или перейти на 16-разрядный ЦП в 32-разрядном сегменте.

Атрибутам **USE32** и **Flat** должны предшествовать директивы процессора. 386 или более поздней версии.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
