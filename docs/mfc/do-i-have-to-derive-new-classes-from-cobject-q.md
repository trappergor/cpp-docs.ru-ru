---
title: Необходимо ли создавать новые классы как производные от CObject? | Документы Майкрософт
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
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec080e556b57afadbc3d958f4dba5ac6393108aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408912"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Необходимо ли создавать новые классы как производные от CObject?

Нет, это не так.

Наследуйте класс от [CObject](../mfc/reference/cobject-class.md) при необходимости помещениях, он предоставляет, например сериализации или динамические creatability. Многие классы данных необходимо сериализовать в файлы, поэтому часто рекомендуется наследовать их из `CObject`. Для примера класса, производного от `CObject`, см. в разделе [пример Scribble](../visual-cpp-samples.md).

## <a name="see-also"></a>См. также

[Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
