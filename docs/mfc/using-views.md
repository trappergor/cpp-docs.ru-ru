---
title: Использование представлений
ms.date: 11/04/2016
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
ms.openlocfilehash: 81668f7409f2b1a4480bde958dc06ce1156e03fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411426"
---
# <a name="using-views"></a>Использование представлений

Функции представления являются графического отображения данных документа для пользователя, а также принимать и интерпретации введенных пользователем данных в качестве операций над документом. Задачи в писать класс представления должны:

- Написать класс представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функция-член, который отображает данные документа.

- Соединиться функции-члены обработчика сообщений в классе представления соответствующих сообщений Windows и объекты пользовательского интерфейса, например пунктах меню.

- Реализуйте эти обработчики для интерпретации введенных пользователем данных.

Кроме того, может потребоваться переопределить другие `CView` функции-члены в классе производным представлением. В частности, может потребоваться переопределить [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) для выполнения специальной инициализации для представления и [OnUpdate](../mfc/reference/cview-class.md#onupdate) для выполнения специальной обработки необходимы только в том случае, перед представление перерисовывается. Для многостраничных документов, необходимо также переопределить [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) инициализировать диалоговое окно печати с числом печатаемых страниц и другие сведения. Дополнительные сведения о переопределении `CView` функций-членов см. Описание класса [CView](../mfc/reference/cview-class.md) в *Справочник по библиотеке MFC*.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Производные классы представлений доступные в MFC](../mfc/derived-view-classes-available-in-mfc.md)

- [Рисование в представлении](../mfc/drawing-in-a-view.md)

- [Интерпретация ввода пользователя через представление](../mfc/interpreting-user-input-through-a-view.md)

- [Роль просмотра при печати](../mfc/role-of-the-view-in-printing.md)

- [Масштаба и прокрутка представлений](../mfc/scrolling-and-scaling-views.md)

- [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>См. также

[Архитектура документа/обзора](../mfc/document-view-architecture.md)<br/>
[Класс CFormView](../mfc/reference/cformview-class.md)<br/>
[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Обход механизма сериализации](../mfc/bypassing-the-serialization-mechanism.md)
