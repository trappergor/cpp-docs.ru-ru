---
title: Использование функции abort | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Abort
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3edc24b2b8dc869022039d4aaaea73af06eac16b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092547"
---
# <a name="using-abort"></a>Использование функции abort

Вызов [прервать](../c-runtime-library/reference/abort.md) функции приводит к немедленному завершению. Выполняется обход нормального процесса удаления для инициализированных глобальных статических объектов. Также осуществляется обход всей специальной обработки, которая была задана с помощью функции `atexit`.

## <a name="see-also"></a>См. также

[Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)