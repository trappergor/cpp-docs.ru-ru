---
title: "Макросы MFC и глобальные | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eeb53dea24ccd4d34ef90045e3254915135e70c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-macros-and-globals"></a>Макросы и глобальные объекты MFC
Библиотеки классов Microsoft Foundation можно разделить на два основных раздела: (1) классы MFC и (2) макросы и глобальные переменные. Если функция или переменная не является членом класса, это глобальная функция или переменная.  
  
 Библиотека MFC и Active Template Library (ATL) совместно использовать макросы преобразования строк. Дополнительные сведения см. в разделе [макросы преобразования строк](../../atl/reference/string-conversion-macros.md) в ATL документации.  
  
 Макросы MFC и глобальные объекты предоставляют функциональность по следующим категориям.  
  
## <a name="general-mfc"></a>Общие MFC  
  
-   [Типы данных](data-types-mfc.md)  
  
-   [Приведение типов объектов классов MFC](type-casting-of-mfc-class-objects.md)  
  
-   [Службы модели объекта во время выполнения](run-time-object-model-services.md)  
  
-   [Диагностические службы](diagnostic-services.md)  
  
-   [Обработка исключений](exception-processing.md)  
  
-   [Форматирование CString и отображение окна сообщения](cstring-formatting-and-message-box-display.md)  
  
-   [Схемы сообщений](message-map-macros-mfc.md)  

-   [Делегат и схемы интерфейсов](delegate-and-interface-maps.md)

-   [Модули и библиотеки DLL](extension-dll-macros.md)
  
-   [Сведения о приложении и управление](application-information-and-management.md)  
  
-   [Стандартная команда и окно идентификаторы](standard-command-and-window-ids.md)  
  
-   [Вспомогательные функции классов коллекции](collection-class-helpers.md)  
  
-   [Функции серого цвета и сглаживания точечного рисунка](gray-and-dithered-bitmap-functions.md)  
  
-   [Стандартные программы диалоговых окон данных exchange (DDX)](standard-dialog-data-exchange-routines.md)  
  
-   [Процедуры проверки (DDV) данных стандартное диалоговое окно](standard-dialog-data-validation-routines.md)  
  
-   [Сообщения AFX](afx-messages.md)  
  
-   [Стили элемента управления панели инструментов](toolbar-control-styles.md)  
  
-   [Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>База данных  
  
-   [Запишите обмен полей (RFX) функции](record-field-exchange-functions.md) и [блочный обмен полей записей (bulk RFX) функции](record-field-exchange-functions.md) для классов MFC ODBC  
  
-   [Функции обмена данными (DFX) полями записи](record-field-exchange-functions.md) для классов MFC DAO  
  
-   [Функции обмена данными диалогового окна (DDX) для CRecordView и CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (классы MFC ODBC и DAO)  
  
-   [Обмена данными диалоговых (окон DDX) функции для элементов управления OLE](dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Макросы и глобальные объекты для помощи в прямой вызов функций Open Database Connectivity (ODBC) API](database-macros-and-globals.md)  
  
-   [Инициализация ядра базы данных DAO и завершение](dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Интернет  
  
-   [Глобальные объекты разбора URL-адрес](internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML / схемы событий DHTML  
  
-   [Ошибка обмена данными диалогового окна DHTML вспомогательных макросов (диалоговых окон DDX)](ddx-dhtml-helper-macros.md)  
  
-   [Схемы событий DHTML](dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [Инициализация OLE](ole-initialization.md)  
  
-   [Элемент управления приложением](application-control.md)  
  
-   [Схемы подготовки к отправке](dispatch-maps.md)  
  
 Кроме того, MFC предоставляет функции, вызываемой [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) , OLE-контейнер, разработанных с помощью MFC 4.0 для полной поддержки включает встроенные элементы управления OLE.  
  
## <a name="ole-controls"></a>Элементы управления OLE  
  
-   [Константы типа параметра Variant](variant-parameter-type-constants.md)  
  
-   [Доступ к библиотеке типов](type-library-access.md)  
  
-   [Страницы свойств](property-pages-mfc.md)  
  
-   [Схемы событий](event-maps.md)  
  
-   [Схемы приемников событий](event-sink-maps.md)  
  
-   [Схемы подключения](connection-maps.md)  
  
-   [Регистрация элементов управления OLE](registering-ole-controls.md)  
  
-   [Фабрики классов и прослушивание](class-factories-and-licensing.md)  
  
-   [Сохраняемость элементов управления OLE](persistence-of-ole-controls.md)  
  
 Первая часть этого раздела краткое описание каждого из перечисленных выше категорий и списки, глобальные переменные и макросы в категории, а также краткое описание функций. После этого описаны глобальные функции, глобальные переменные и макросы в библиотеке MFC.  
  
> [!NOTE]
>  Многие глобальные функции начинаются с префикса «Afx», но некоторые из них, например, функции обмена данными (диалоговых окон DDX) данных диалогового окна и многие из функций базы данных, не соответствуют этому соглашению. Все глобальные переменные начинаться с «afx» как префикс. Макросы не начинаются с любого определенного префикса, но они записываются прописными буквами.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../mfc/class-library-overview.md)



