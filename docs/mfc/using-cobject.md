---
title: Использование CObject
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: 15b5bebb8e75d24b769cd29971d08b3fbf92fcf8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302134"
---
# <a name="using-cobject"></a>Использование CObject

[CObject](../mfc/reference/cobject-class.md) является корневой базовый класс для большинства из Microsoft Foundation Class Library (MFC). `CObject` Класс содержит множество полезных функций, которые можно внедрить в собственные объекты программы, включая поддержку сериализации, сведения о классе среды выполнения и диагностических выходных данных объекта. Если вы наследуете от класса `CObject`, ваш класс может использовать эти `CObject` функции.

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

- [Создать класс, производный от CObject](../mfc/deriving-a-class-from-cobject.md)

- [Добавить поддержку сведения о классе среды выполнения, динамическое создание и сериализации для моего производного класса](../mfc/specifying-levels-of-functionality.md)

- [Сведения о классе во время выполнения доступ](../mfc/accessing-run-time-class-information.md)

- [Динамическое создание объектов](../mfc/dynamic-object-creation.md)

- [Дамп объекта данных для диагностики](/previous-versions/visualstudio/visual-studio-2010/sc15kz85)

- Проверка внутреннего состояния объекта (см. в разделе [MFC ASSERT_VALID и CObject::AssertValid](reference/diagnostic-services.md#assert_valid))

- [Класс сериализоваться в постоянное хранилище](../mfc/serialization-in-mfc.md)

- Просмотреть список [CObject часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[Структура CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)<br/>
[Файлы](../mfc/files-in-mfc.md)<br/>
[Сериализация](../mfc/serialization-in-mfc.md)
