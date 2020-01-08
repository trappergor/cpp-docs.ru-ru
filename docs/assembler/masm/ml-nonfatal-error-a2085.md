---
title: Некритичная ошибка ML A2085
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: f8fdedfc1bc8bff63124d18fe1410d9f144cb926
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316841"
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085

**Инструкция или регистр не приняты в текущем режиме ЦП**

Предпринята попытка использовать инструкцию, регистр или ключевое слово, которое недопустимо для текущего режима процессора.

Например, для 32-битных регистров требуется [386](dot-386.md) или более поздняя версия. Для контрольных регистров, таких как CR0, требуется привилегированный режим [. 386P](dot-386p.md) или выше. Эта ошибка также будет создана для ключевых слов **NEAR32**, **FAR32**и **Flat** , для которых требуется. **386** или более поздней версии.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
