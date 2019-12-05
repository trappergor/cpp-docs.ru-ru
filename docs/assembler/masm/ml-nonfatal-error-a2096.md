---
title: Некритичная ошибка ML A2096
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: 14fb30214cf7badf51368672dc52635d50a067f1
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855478"
---
# <a name="ml-nonfatal-error-a2096"></a>Некритичная ошибка ML A2096

**Ожидался регистр сегмента, группы или сегмента**

Ожидался сегмент или группа, но он не найден.

Произошла одна из следующих ошибок:

- Левый операнд, заданный оператором переопределения сегмента ( **:** ), не был регистром сегмента (CS, DS, SS, ES, FS или GS), именем группы, именем сегмента или выражением сегмента.

- Директиве " [предположить](../../assembler/masm/assume.md) " был присвоен регистр сегмента без допустимого адреса сегмента, регистра сегмента, группы или специальной **плоской** группы.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>