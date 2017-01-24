---
title: "Макросы и глобальные объекты MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Afx - соглашение об именовании"
  - "глобальные функции"
  - "глобальные функции, MFC - библиотека"
  - "глобальные переменные, MFC - библиотека"
  - "макросы"
  - "макросы, MFC - библиотека"
  - "MFC - библиотека, глобальные функции и переменные"
  - "MFC - библиотека, макросы"
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Макросы и глобальные объекты MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Библиотеки Microsoft Foundation Class можно разделить на 2 основного раздела: классы MFC \(1\) и \(2\) и макросы globals.  Если функция или переменная не является членом класса, функция или глобальная переменная.  
  
 Библиотека MFC и библиотека шаблонных классов ATL \(ATL\) используют макросы преобразования строк.  Дополнительные сведения см. в разделе [String Conversion Macros](../../atl/reference/string-conversion-macros.md) документации пакета ATL.  
  
 Макросы и globals MFC предоставляют функции в следующих категорий.  
  
## Общий MFC  
  
-   [Типы данных](../Topic/Data%20Types%20\(MFC\).md)  
  
-   [Приведение типов объектов классов MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [Службы объектной модели среды выполнения](../../mfc/reference/run-time-object-model-services.md)  
  
-   [Службы диагностики](../Topic/Diagnostic%20Services.md)  
  
-   [Обработка исключений](../../mfc/reference/exception-processing.md)  
  
-   [Форматирование CString и отображение окна сообщения](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [Схемы сообщений](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [Данные и управлению приложения](../Topic/Application%20Information%20and%20Management.md)  
  
-   [Стандартных идентификаторов команд и окна](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [Вспомогательных классов коллекций](../../mfc/reference/collection-class-helpers.md)  
  
-   [Серые и сглаженные функции растрового изображения](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [Стандартные процедуры обмена данных \(DDX\)](../Topic/Standard%20Dialog%20Data%20Exchange%20Routines.md)  
  
-   [Стандартные процедуры \(DDV\) проверки данных диалогового окна](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [Сообщения AFX](../../mfc/reference/afx-messages.md)  
  
-   [Стили элемента управления панели инструментов](../Topic/ToolBar%20Control%20Styles.md)  
  
-   [Перечисление CMFCImagePaintArea::IMAGE\_EDIT\_MODE](../Topic/CMFCImagePaintArea::IMAGE_EDIT_MODE%20Enumeration.md)  
  
## База данных  
  
-   [Функции обмена полями записей \(RFX\)](../../mfc/reference/record-field-exchange-functions.md) и [Функции блочного обмена полями записей \(RFX\) навального](../../mfc/reference/record-field-exchange-functions.md) для классов ODBC  
  
-   [Функции обмена полями записей \(DFX\)](../../mfc/reference/record-field-exchange-functions.md) для классов MFC DAO  
  
-   [Функции обмена данными с диалоговым окном DDX для CRecordView и CDaoRecordView](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) \(Классы MFC DAO и ODBC\)  
  
-   [Функции обмена данных \(DDX\) для элементов управления OLE](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Макросы и globals для содействия в вызов функции API ODBC \(ODBC\) непосредственно](../../mfc/reference/database-macros-and-globals.md)  
  
-   [Инициализации и завершения ядра СУБД DAO](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## Internet  
  
-   [URL\-адрес в интернете анализа globals](../Topic/Internet%20URL%20Parsing%20Globals.md)  
  
## Сопоставления событий DHTML\/DHTML  
  
-   [Обмен данными в диалоговых окнах DHTML DDX вспомогательных макросов](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [Сопоставления событий DHTML](../../mfc/reference/dhtml-event-maps.md)  
  
## OLE  
  
-   [Инициализация OLE](../../mfc/reference/ole-initialization.md)  
  
-   [Элемент управления приложениями](../../mfc/reference/application-control.md)  
  
-   [Схемы подготовки к отправке](../../mfc/reference/dispatch-maps.md)  
  
 Кроме того, MFC предоставляет функцию [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md), которая включает любое OLE\-контейнер развитое с MFC 4.0 полностью для поддержки внедренные элементы управления OLE.  
  
## Элементы управления OLE  
  
-   [Различные константы типа параметра](../Topic/Variant%20Parameter%20Type%20Constants.md)  
  
-   [Доступ библиотеки типов](../../mfc/reference/type-library-access.md)  
  
-   [Страницы свойств](../../mfc/reference/property-pages-mfc.md)  
  
-   [Сопоставления событий](../../mfc/reference/event-maps.md)  
  
-   [Сопоставления приемника событий](../../mfc/reference/event-sink-maps.md)  
  
-   [Сопоставления подключения](../../mfc/reference/connection-maps.md)  
  
-   [Для регистрации элемента управления OLE](../Topic/Registering%20OLE%20Controls.md)  
  
-   [Фабрики класса и лицензирование](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [Сохранение элементов управления OLE](../../mfc/reference/persistence-of-ole-controls.md)  
  
 В первой части этого раздела краткое описание каждой из предыдущих категорий и перечислены globals и макросы в категории с краткими описаниями функциональности.  После этого описания глобальных глобальных переменных, функций и макросов в библиотеке MFC.  
  
> [!NOTE]
>  Запустить несколько глобальных функций с префиксом «Afx», но некоторые данные, например диалогового окна обмен функции DDX и многие функции базы данных, не соответствующие этого соглашения.  Глобальных переменных начинаются с «afx» в качестве префикса.  Макросы не запускаются с любым указанным префиксом, но они написаны прописными буквами.  
  
## См. также  
 [Общие сведения о классах](../../mfc/class-library-overview.md)