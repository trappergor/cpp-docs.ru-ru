---
title: Использование функции abort
ms.date: 11/04/2016
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: e8cc7bce552acf67c0f9bf2025e0040dc051cff6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446415"
---
# <a name="using-abort"></a>Использование функции abort

Вызов функции [Abort](../c-runtime-library/reference/abort.md) приводит к немедленному завершению работы. Выполняется обход нормального процесса удаления для инициализированных глобальных статических объектов. Также осуществляется обход всей специальной обработки, которая была задана с помощью функции `atexit`.

## <a name="see-also"></a>См. также раздел

[Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)