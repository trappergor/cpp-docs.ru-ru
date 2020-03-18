---
title: Использование CObject
ms.date: 11/04/2016
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: b5399f02819407a529fd5ec66d4f5acbb16ca002
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441920"
---
# <a name="using-cobject"></a>Использование CObject

[CObject](../mfc/reference/cobject-class.md) — это корневой базовый класс для большинства Библиотека Microsoft Foundation Class (MFC). Класс `CObject` содержит множество полезных функций, которые может потребоваться включить в собственные объекты программы, включая поддержку сериализации, сведения о классе времени выполнения и данные диагностики объектов. Если класс является производным от `CObject`, класс может использовать эти `CObject` функции.

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

- [Создание производного класса от CObject](../mfc/deriving-a-class-from-cobject.md)

- [Добавление поддержки сведений о классе времени выполнения, динамического создания и сериализации в производный класс](../mfc/specifying-levels-of-functionality.md)

- [Доступ к сведениям о классе времени выполнения](../mfc/accessing-run-time-class-information.md)

- [Динамическое создание объектов](../mfc/dynamic-object-creation.md)

- [Дамп данных объекта в целях диагностики](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))

- Проверка внутреннего состояния объекта (см. раздел [MFC ASSERT_VALID и CObject:: AssertValid](reference/diagnostic-services.md#assert_valid))

- [Сериализация класса в постоянное хранилище](../mfc/serialization-in-mfc.md)

- См. список [часто задаваемых вопросов о CObject](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>См. также раздел

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[Структура CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)<br/>
[Файлы](../mfc/files-in-mfc.md)<br/>
[Сериализация](../mfc/serialization-in-mfc.md)
