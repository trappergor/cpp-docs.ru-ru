---
title: "Макросы MFC и глобальные объекты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- global functions
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d26b374e233326ac5acc97486edc8d38e6bf5d81
ms.openlocfilehash: 75db28c7be1ab497ba9656136d22b114b488c4ae
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-macros-and-globals"></a>Макросы и глобальные объекты MFC
Библиотеки классов Microsoft Foundation можно разделить на два основных раздела: (1) классы MFC и (2) макросы и глобальные переменные. Если функция или переменная не является членом класса, это глобальная функция или переменная.  
  
 Библиотеки MFC и Active Template Library (ATL) используют макросы преобразования строк. Дополнительные сведения см. в разделе [макросы преобразования строк](../../atl/reference/string-conversion-macros.md) в ATL документации.  
  
 Макросы MFC и глобальные объекты предоставляют функциональность по следующим категориям.  
  
## <a name="general-mfc"></a>Общие MFC  
  
-   [Типы данных](../../mfc/reference/data-types-mfc.md)  
  
-   [Приведение типов объектов классов MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [Службы модели объекта во время выполнения](../../mfc/reference/run-time-object-model-services.md)  
  
-   [Диагностические службы](../../mfc/reference/diagnostic-services.md)  
  
-   [Обработка исключений](../../mfc/reference/exception-processing.md)  
  
-   [Форматирование CString и отображение окна сообщения](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [Схемы сообщений](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [Сведения о приложении и управление](../../mfc/reference/application-information-and-management.md)  
  
-   [Стандартные идентификаторы команд и окна](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [Вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md)  
  
-   [Функции серого цвета и сглаживания точечного рисунка](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [Стандартные программы диалоговых окон данных exchange (DDX)](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [Процедуры проверки (DDV) данных стандартного диалогового окна](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [Сообщения AFX](../../mfc/reference/afx-messages.md)  
  
-   [Стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md)  
  
-   [Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>База данных  
  
-   [Запись функций Exchange полей (RFX)](../../mfc/reference/record-field-exchange-functions.md) и [блочный обмен полей записей (bulk RFX) функции](../../mfc/reference/record-field-exchange-functions.md) для классов MFC ODBC  
  
-   [Функции exchange (DFX) полями записи](../../mfc/reference/record-field-exchange-functions.md) для классов MFC DAO  
  
-   [Обмен данными (диалоговых окон DDX) функции для CRecordView и CDaoRecordView](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (классы MFC ODBC и DAO)  
  
-   [Обмена данными диалоговых (окон DDX) функции для элементов управления OLE](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Макросы и глобальные функции для помощи в прямой вызов функций Open Database Connectivity (ODBC) API](../../mfc/reference/database-macros-and-globals.md)  
  
-   [Инициализация ядра базы данных DAO и прекращение работы](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Интернет  
  
-   [Глобальные объекты разбора URL Интернета](../../mfc/reference/internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML и схемы событий DHTML  
  
-   [Обмена данными DHTML диалоговых (окон DDX) вспомогательных макросов](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [Схемы событий DHTML](../../mfc/reference/dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [Инициализация OLE](../../mfc/reference/ole-initialization.md)  
  
-   [Управление приложениями](../../mfc/reference/application-control.md)  
  
-   [Схемы подготовки к отправке](../../mfc/reference/dispatch-maps.md)  
  
 Кроме того, MFC предоставляет функцию с именем [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b) что OLE-контейнер, разработанные с использованием MFC 4.0 для полной поддержки включает встроенные элементы управления OLE.  
  
## <a name="ole-controls"></a>Элементы управления OLE  
  
-   [Константы типа параметра Variant](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [Доступ к библиотеке типов](../../mfc/reference/type-library-access.md)  
  
-   [Страницы свойств](../../mfc/reference/property-pages-mfc.md)  
  
-   [Схемы событий](../../mfc/reference/event-maps.md)  
  
-   [Схемы приемников событий](../../mfc/reference/event-sink-maps.md)  
  
-   [Схемы подключения](../../mfc/reference/connection-maps.md)  
  
-   [Регистрация элементов управления OLE](../../mfc/reference/registering-ole-controls.md)  
  
-   [Фабрики классов и прослушивание](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [Сохраняемость элементов управления OLE](../../mfc/reference/persistence-of-ole-controls.md)  
  
 Первая часть этого раздела кратко описываются каждого из приведенных выше категорий и перечислены глобальные переменные и макросы в категории, а также краткие описания функциональности. После этого описаны глобальные функции, глобальные переменные и макросы в библиотеке MFC.  
  
> [!NOTE]
>  Многие глобальные функции начинаются с префикса «Afx», но некоторые из них, например, диалогового окна (DDX) функции обмена данными и многие из функций базы данных, не соответствуют этому соглашению. Все глобальные переменные начинаться с «afx» как префикс. Макросы не начинаются с любой определенный префикс, но они записываются прописными буквами.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../mfc/class-library-overview.md)




