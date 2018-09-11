---
title: Некритичная ошибка ML A2085 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd5ec9f36a4f956b8eeb097b6a8f8eaed89ba2b2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681440"
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085

**инструкция или регистрация, не принимается в текущем режиме ЦП**

Была предпринята попытка использовать инструкции, регистр или ключевое слово, которое недопустимо для текущего режима процессора.

Например, требуется 32-разрядные регистры [.386](../../assembler/masm/dot-386.md) или более поздней версии. Регистрирует элемент управления, например CR0 потребовать наличия привилегированный режим [.386P](../../assembler/masm/dot-386p.md) или более поздней версии. Эта ошибка может также возникать для **NEAR32**, **FAR32**, и **НЕСТРУКТУРИРОВАННЫЙ** ключевые слова, которые требуют. **386** или более поздней версии.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>