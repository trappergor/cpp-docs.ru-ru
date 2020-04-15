---
title: Макросы и глобальные объекты MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
ms.openlocfilehash: ed45fc7014bda18887be6dc8fbcdff8ba9a9c5f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373045"
---
# <a name="mfc-macros-and-globals"></a>Макросы и глобальные объекты MFC

Библиотека класса Фонда Майкрософт может быть разделена на два основных раздела: (1) классы MFC и (2) макросы и глобальные. Если функция или переменная не является членом класса, это глобальная функция или переменная.

Библиотека MFC и Библиотека Active Template Library (ATL) делятся макросами преобразования строк. Для получения дополнительной информации смотрите в документации ATL [строки преобразования.](../../atl/reference/string-conversion-macros.md)

Макросы и глобалы MFC предлагают функциональность в следующих категориях.

## <a name="general-mfc"></a>Генеральный МФЦ

- [Типы данных](data-types-mfc.md)

- [Тип литья объектов класса МФЦ](type-casting-of-mfc-class-objects.md)

- [Услуги модели объектов времени в течение выполнения](run-time-object-model-services.md)

- [Диагностические услуги](diagnostic-services.md)

- [Обработка исключений](exception-processing.md)

- [Форматирование CString и отображение окна сообщения](cstring-formatting-and-message-box-display.md)

- [Карты сообщений](message-map-macros-mfc.md)

- [Карты делегатов и интерфейсов](delegate-and-interface-maps.md)

- [Модули и библиотеки DLL](extension-dll-macros.md)

- [Информация о применении и управление](application-information-and-management.md)

- [Стандартная команда и идентификаторы окон](standard-command-and-window-ids.md)

- [Помощники класса коллекции](collection-class-helpers.md)

- [Функции серого цвета и сглаживания точечного рисунка](gray-and-dithered-bitmap-functions.md)

- [Стандартный диалоговый обмен данными (DDX)](standard-dialog-data-exchange-routines.md)

- [Стандартная проверка данных диалогов (DDV)](standard-dialog-data-validation-routines.md)

- [Сообщения AFX](afx-messages.md)

- [Стили управления панели инструментов](toolbar-control-styles.md)

- [Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>База данных

- [Функции биржи звукозаписи (RFX)](record-field-exchange-functions.md) и [массовая биржа полевых данных (bulk RFX)](record-field-exchange-functions.md) для классов MFC ODBC

- [Функции обмена полями записи (DFX)](record-field-exchange-functions.md) для классов MFC DAO

- [Диалог обмена данными (DDX) функции для CRecordView и CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC и DAO классов)

- [Диалог обмена данными (DDX) функции для управления OLE](dialog-data-exchange-functions-for-ole-controls.md)

- [Макрос и глобальные, чтобы помочь в вызове Open Database Connectivity (ODBC) API функции непосредственно](database-macros-and-globals.md)

- [Инициализация и прекращение работы движка базы данных DAO](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>Интернет

- [Интернет URL разбора глобалов](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML / DHTML Карты событий

- [Обмен данными диалогов DHTML (DDX)](ddx-dhtml-helper-macros.md)

- [Карты событий DHTML](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [Инициализация OLE](ole-initialization.md)

- [управление приложениями;](application-control.md)

- [Схемы подготовки к отправке](dispatch-maps.md)

Кроме того, MFC предоставляет функцию под названием [AfxEnableControlContainer,](ole-initialization.md#afxenablecontrolcontainer) которая позволяет любому контейнеру OLE, разработанной с MFC 4.0, полностью поддерживать встроенные элементы управления OLE.

## <a name="ole-controls"></a>Элементы управления OLE

- [Константы типа параметра варианта](variant-parameter-type-constants.md)

- [Введите доступ к библиотеке](type-library-access.md)

- [Страницы свойств](property-pages-mfc.md)

- [Схемы событий](event-maps.md)

- [Схемы приемников событий](event-sink-maps.md)

- [Карты подключения](connection-maps.md)

- [Регистрация элементов управления OLE](registering-ole-controls.md)

- [Фабрики классов и лицензирование](class-factories-and-licensing.md)

- [Сохраняемость элементов управления OLE](persistence-of-ole-controls.md)

В первой части этого раздела кратко рассматриваются каждая из предыдущих категорий и перечислены глобальные и макросы в категории, а также краткое описание функциональности. Ниже приведены описания глобальных функций, глобальных переменных и макросов в библиотеке MFC.

> [!NOTE]
> Многие глобальные функции начинаются с приставки "Afx", но некоторые, например, функции обмена диалоговыми данными (DDX) и многие функции базы данных не соответствуют этой конвенции. Все глобальные переменные начинаются с "afx" в качестве префикса. Макрос ы не начинаются с какой-либо конкретной префикс, но они написаны буквами верхнего регистра.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../mfc/class-library-overview.md)
