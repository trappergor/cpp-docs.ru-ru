---
title: Некритичная ошибка ML A2085
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 729f6f38761171c6ddc4cccfc2443c6a2b597bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177192"
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085

**инструкция или регистрация, не принимается в текущем режиме ЦП**

Была предпринята попытка использовать инструкции, регистр или ключевое слово, которое недопустимо для текущего режима процессора.

Например, требуется 32-разрядные регистры [.386](../../assembler/masm/dot-386.md) или более поздней версии. Регистрирует элемент управления, например CR0 потребовать наличия привилегированный режим [.386P](../../assembler/masm/dot-386p.md) или более поздней версии. Эта ошибка может также возникать для **NEAR32**, **FAR32**, и **НЕСТРУКТУРИРОВАННЫЙ** ключевые слова, которые требуют. **386** или более поздней версии.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>