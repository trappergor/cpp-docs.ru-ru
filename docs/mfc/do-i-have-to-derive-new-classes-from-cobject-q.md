---
title: Необходимо ли создавать новые классы как производные от CObject?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: cbefed5f44981d784d1fc5b6616bab5ee45e4115
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279514"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Необходимо ли создавать новые классы как производные от CObject?

Нет, это не так.

Наследуйте класс от [CObject](../mfc/reference/cobject-class.md) при необходимости помещениях, он предоставляет, например сериализации или динамические creatability. Многие классы данных необходимо сериализовать в файлы, поэтому часто рекомендуется наследовать их из `CObject`. Для примера класса, производного от `CObject`, см. в разделе [пример Scribble](../visual-cpp-samples.md).

## <a name="see-also"></a>См. также

[Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
