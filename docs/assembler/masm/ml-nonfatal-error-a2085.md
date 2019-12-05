---
title: Некритичная ошибка ML A2085
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3bd89fb2b7f8b755cdb095e63ed89386332ecf9d
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855762"
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085

**Инструкция или регистр не приняты в текущем режиме ЦП**

Предпринята попытка использовать инструкцию, регистр или ключевое слово, которое недопустимо для текущего режима процессора.

Например, для 32-битных регистров требуется [386](../../assembler/masm/dot-386.md) или более поздняя версия. Для контрольных регистров, таких как CR0, требуется привилегированный режим [. 386P](../../assembler/masm/dot-386p.md) или выше. Эта ошибка также будет создана для ключевых слов **NEAR32**, **FAR32**и **Flat** , для которых требуется. **386** или более поздней версии.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>