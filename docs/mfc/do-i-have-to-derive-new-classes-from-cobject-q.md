---
title: Необходимо ли создавать новые классы как производные от CObject?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: d38e589f371fc56f5566c56de7b19c366065a503
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446925"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Необходимо ли создавать новые классы как производные от CObject?

Нет, нет.

Создавайте класс от [CObject](../mfc/reference/cobject-class.md) , если вам нужны предоставляемые им средства, такие как сериализация или динамическое создание. Многие классы данных должны быть сериализованы в файлы, поэтому зачастую рекомендуется наследовать их от `CObject`. Пример класса, производного от `CObject`, см. в [образце Scribble](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>См. также раздел

[Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
