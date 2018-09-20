---
title: Каковы издержки при наследовании классов от CObject? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e41f9060ce24b89a0a7faae54ca6207c740475f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443245"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Каковы издержки при наследовании классов от CObject?

Затраты на наследование от класса [CObject](../mfc/reference/cobject-class.md) сводится к минимуму. Производный класс наследует только четыре виртуальных функций и одним [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) объекта.

## <a name="see-also"></a>См. также

[Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
