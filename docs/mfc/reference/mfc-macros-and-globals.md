---
title: Макросы и глобальные объекты MFC
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
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
ms.openlocfilehash: 2dfb2c1c5062f742b728ea651a292be84e33f6d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566781"
---
# <a name="mfc-macros-and-globals"></a>Макросы и глобальные объекты MFC

Библиотеки Microsoft Foundation Class можно разделить на два основных раздела: (1 классы MFC и (2) макросы и глобальные объекты. Если функция или переменная не является членом класса, это глобальной функции или переменной.

Библиотеки MFC и Active Template Library (ATL) используют макросы преобразования строк. Дополнительные сведения см. в разделе [макросы преобразования строк](../../atl/reference/string-conversion-macros.md) в документации по ATL.

Макросы и globals MFC предлагают функции в следующих категориях.

## <a name="general-mfc"></a>Общие MFC

- [Типы данных](data-types-mfc.md)

- [Приведение типов объектов классов MFC](type-casting-of-mfc-class-objects.md)

- [Службы модели объекта во время выполнения](run-time-object-model-services.md)

- [Диагностические службы](diagnostic-services.md)

- [Обработка исключений](exception-processing.md)

- [Форматирование CString и отображение окна сообщения](cstring-formatting-and-message-box-display.md)

- [Схемы сообщений](message-map-macros-mfc.md)

- [Делегат и схемы интерфейсов](delegate-and-interface-maps.md)

- [Модули и библиотеки DLL](extension-dll-macros.md)

- [Сведения о приложении и управления](application-information-and-management.md)

- [Стандартные идентификаторы команд и окна](standard-command-and-window-ids.md)

- [Вспомогательные функции классов коллекции](collection-class-helpers.md)

- [Функции серого цвета и сглаживания точечного рисунка](gray-and-dithered-bitmap-functions.md)

- [Стандартные данные exchange (DDX) диалоговых окон](standard-dialog-data-exchange-routines.md)

- [Стандартные данные проверки (DDV) диалоговых окон](standard-dialog-data-validation-routines.md)

- [Сообщения AFX](afx-messages.md)

- [Стили элемента управления панели инструментов](toolbar-control-styles.md)

- [Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>База данных

- [Функции Exchange полей (RFX) записей](record-field-exchange-functions.md) и [блочный обмен полей записей (bulk RFX) функции](record-field-exchange-functions.md) для классов MFC ODBC

- [Функции exchange (DFX) поля записей](record-field-exchange-functions.md) для классов MFC DAO

- [Обмен данными диалоговых окон (DDX) функции для CRecordView и CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (классы MFC ODBC и DAO)

- [Ошибка обмена данными диалоговых (окон DDX) функции для элементов управления OLE](dialog-data-exchange-functions-for-ole-controls.md)

- [Макросы и глобальные объекты, помогающих в прямой вызов функций Open Database Connectivity (ODBC) API](database-macros-and-globals.md)

- [Инициализация ядра базы данных DAO и завершение](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>Интернет

- [URL-адрес, глобальные объекты разбора](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML / схемы событий DHTML

- [Вспомогательные макросы (DDX) обмена данными диалоговых DHTML](ddx-dhtml-helper-macros.md)

- [Схемы событий DHTML](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [Инициализация OLE](ole-initialization.md)

- [Управление приложениями](application-control.md)

- [Схемы подготовки к отправке](dispatch-maps.md)

Кроме того, MFC предоставляет функции с именем [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) что OLE-контейнер, разработанные с использованием MFC 4.0 для полной поддержки позволяет внедрять элементов управления OLE.

## <a name="ole-controls"></a>Элементы управления OLE

- [Константы типа параметра Variant](variant-parameter-type-constants.md)

- [Доступ к библиотеке типов](type-library-access.md)

- [Страницы свойств](property-pages-mfc.md)

- [Схемы событий](event-maps.md)

- [Схемы приемников событий](event-sink-maps.md)

- [Схемы подключения](connection-maps.md)

- [Регистрация элементов управления OLE](registering-ole-controls.md)

- [Фабрики классов и лицензирование](class-factories-and-licensing.md)

- [Сохраняемость элементов управления OLE](persistence-of-ole-controls.md)

В первой части в этом разделе кратко рассматривается каждая из перечисленных выше категорий и перечислены глобальные переменные и макросы в категории, а также краткие описания функциональности. Следуя инструкциям из этого описаны глобальные функции, глобальные переменные и макросы в библиотеке MFC.

> [!NOTE]
>  Множество глобальных функций начинаются с префикса «Afx», но некоторые из них, например, функции exchange (DDX) данными диалоговых окон и многие из функций базы данных, не соответствуют этому соглашению. Все глобальные переменные начинаются со знака «afx» как префикс. Макросы не начинаются с какого-либо определенного префикса, но они записываются прописными буквами.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../mfc/class-library-overview.md)

