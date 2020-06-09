---
title: Необходимо ли создавать новые классы как производные от CObject?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: 371ede0f0921182c066b4cb224e66b18eb6f1208
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616741"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Необходимо ли создавать новые классы как производные от CObject?

Нет, нет.

Создавайте класс от [CObject](reference/cobject-class.md) , если вам нужны предоставляемые им средства, такие как сериализация или динамическое создание. Многие классы данных должны быть сериализованы в файлы, поэтому часто рекомендуется наследовать их от `CObject` . Пример класса, производного от `CObject` , см. в [образце Scribble](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>См. также раздел

[Класс CObject. Часто задаваемые вопросы](cobject-class-frequently-asked-questions.md)
