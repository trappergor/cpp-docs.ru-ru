---
title: Некритичная ошибка ML A2031
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2031
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
ms.openlocfilehash: 794fb31fbc22bdefddf9f19e6efcb3c34bbc1861
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431893"
---
# <a name="ml-nonfatal-error-a2031"></a>Некритичная ошибка ML A2031

**должен быть регистром индекса или base**

Была предпринята попытка использовать регистр, который не был базовым или индексным регистром в выражении памяти.

Например следующие выражения вызывают эту ошибку:

```asm
[ax]
[bl]
```

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>