---
title: Использование представлений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcf4af038617cce8326a3e63ba9b4ea66c277f66
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442101"
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

