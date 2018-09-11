---
title: Некритичная ошибка ML A2206 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2206
dev_langs:
- C++
helpviewer_keywords:
- A2206
ms.assetid: 711846d0-5a09-4353-8857-60588c25526a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10edbe68ca7f0093cdeb6a9ca5a02cde07f556e6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676352"
---
# <a name="ml-nonfatal-error-a2206"></a>Некритичная ошибка ML A2206

**отсутствует оператор в выражении**

Не удается вычислить выражение, так как отсутствует оператор. Это сообщение об ошибке также может быть побочным результатом ошибки выше в программе.

Следующая строка будет вызывать такую ошибку:

```asm
value1 = ( 1 + 2 ) 3
```

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>