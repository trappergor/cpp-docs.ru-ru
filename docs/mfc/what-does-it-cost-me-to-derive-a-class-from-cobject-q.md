---
title: Каковы издержки при наследовании классов от CObject?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 521b6a32e3e5b34b4da9dab3117d55a728bd8e88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500455"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Каковы издержки при наследовании классов от CObject?

Затраты на наследование от класса [CObject](../mfc/reference/cobject-class.md) сводится к минимуму. Производный класс наследует только четыре виртуальных функций и одним [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) объекта.

## <a name="see-also"></a>См. также

[Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
