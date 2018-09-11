---
title: Некритичная ошибка ML A2008 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2008
dev_langs:
- C++
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 774cf4c2a51bf084fb63e572cc99b0c8e3cba26f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679379"
---
# <a name="ml-nonfatal-error-a2008"></a>Некритичная ошибка ML A2008

**Синтаксическая ошибка:**

Маркер в текущем положении является причиной синтаксической ошибки.

Мог произойти одно из следующих:

- Префикс точка был добавлен в или из директивы.

- Зарезервированные слова (такие как **C** или **размер**) использовать в качестве идентификатора.

- Использовался инструкции, которые не были доступны с текущим выбором процессора или сопроцессора.

- Во время выполнения оператора сравнения (такие как `==`) был использован в операторе условной сборки вместо оператор сравнения (такие как [EQ](../../assembler/masm/operator-eq.md)).

- Инструкции или директива было задано слишком малое количество операндов.

- Использовался устаревший директиву.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>