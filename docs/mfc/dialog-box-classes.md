---
title: "Классы диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.dialog
dev_langs:
- C++
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d51529e5d04a8297c0d3824ab38c7d2045bc866
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="dialog-box-classes"></a>Классы диалоговых окон
Класс `CDialog` и его производные классы инкапсулируют функциональность диалогового окна. Поскольку диалоговое окно — это особый тип окна, `CDialog` является производным от `CWnd`. Производные классы из диалогового окна `CDialog` или воспользуйтесь одним из классы общих диалоговых окон для стандартных диалоговых окон, таких как открытие или сохранение файла, печать, Выбор шрифта или цвета, запуск операции поиска и замены или с помощью различных связанные с OLE операции.  
  
 [CDialog](../mfc/reference/cdialog-class.md)  
 Базовый класс для всех диалоговых окон, модальные и немодальные.  
  
 [CDataExchange](../mfc/reference/cdataexchange-class.md)  
 Предоставляет сведения об exchange и проверки данных диалоговых окон.  
  
## <a name="common-dialogs"></a>Общие диалоговые окна  
 Эти классы диалоговых окон инкапсулируют общих диалоговых окон Windows. Они предоставляют реализации для использования сложных диалоговых окон.  
  
 [CCommonDialog](../mfc/reference/ccommondialog-class.md)  
 Базовый класс для всех окон.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Предоставляет стандартное диалоговое окно открытия или сохранения файла.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Предоставляет стандартное диалоговое окно для выбора цвета.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Предоставляет стандартное диалоговое окно для выбора шрифта.  
  
 [Диалоговое окно CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)  
 Предоставляет стандартное диалоговое окно для операции поиска и замены.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Предоставляет стандартное диалоговое окно для печати файла.  
  
 [CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)  
 Предоставляет таблицу свойств печати Windows.  
  
 [CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)  
 Инкапсулирует службы, предоставляемые Общие параметры страницы диалоговым окном Windows с дополнительной поддержкой установки и изменения полей печати.  
  
## <a name="ole-common-dialogs"></a>Общие диалоговые окна OLE  
 OLE добавляет некоторые общие диалоговые окна Windows. Эти классы инкапсулируют общие диалоговые окна OLE.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Используется платформой для хранения типичные реализации всех диалоговых окон OLE. Все классы диалоговых окон в категории пользовательского интерфейса являются производными от этого базового класса. `COleDialog`нельзя использовать напрямую.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Отображает диалоговое окно «Вставить объект», стандартный пользовательский интерфейс для вставки новых OLE связанных или внедренных элементов.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Отображает диалоговое окно Специальная вставка стандартный пользовательский интерфейс для реализации команду Специальная вставка.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Отображает диалоговое окно «Изменить ссылки», стандартный пользовательский интерфейс для изменения сведений о связанных элементах.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Отображает диалоговое окно Изменение значка, стандартный пользовательский интерфейс для изменения значок, связанный с OLE-внедренные или связанный элемент.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Отображает диалоговое окно Convert, стандартный пользовательский интерфейс для преобразования OLE-элементы из одного типа в другой.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Инкапсулирует общих свойств OLE диалоговым окном Windows. Общие диалоговые окна свойств OLE предоставляют простой способ отображения и изменения свойств элемента документа OLE в соответствии со стандартами Windows.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Отображает диалоговое окно обновления, стандартный пользовательский интерфейс для обновления всех ссылок в документе. Диалоговое окно содержит индикатор выполнения указывает, насколько близко процедуру обновления для завершения.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Отображает диалоговое окно Изменение источника, стандартный пользовательский интерфейс для изменения назначения и источника связи.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Отображает сервер занят диалоговые окна и сервер не отвечает, стандартный пользовательский интерфейс для обработки вызовов занят приложений. Обычно отображается автоматически [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) реализации.  
  
## <a name="property-sheet-classes"></a>Классы вкладок свойств  
 Классы вкладок свойств позволяют приложения могут использовать страницы свойств, называемые вкладками диалоговых окон. Страницы свойств обеспечивают эффективный способ организации большое количество элементов управления в одном диалоговом окне.  
  
 [CPropertyPage](../mfc/reference/cpropertypage-class.md)  
 Предоставляет отдельные страницы в окне свойств. Производный класс `CPropertyPage` для каждой страницы Добавить вкладку свойств.  
  
 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)  
 Предоставляет кадр для несколько страниц свойств. Является производным класса лист свойств из `CPropertySheet` быстро реализовать вашей страницы свойств.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 В графическом интерфейсе Подобно диалоговому контролировать отображение свойств OLE.  
  
## <a name="html-based-dialog-classes"></a>Классы диалоговых окон, на основе HTML  
 [CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)  
 Используется для создания диалоговых окон, реализовать собственный пользовательский интерфейс с ресурсами HTML, а не в диалоге.  
  
 [CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)  
 Последовательно отображает несколько HTML-страниц и обрабатывает события каждой страницы.  
  
## <a name="related-classes"></a>Связанные классы  
 Эти классы не являются диалоговым окнам сам по себе, но они используют шаблоны диалоговых окон и имеют большую часть поведения диалоговых окон.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Панель элементов управления, который основан на шаблон диалогового окна.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Представление прокрутки, макет которой определяется в шаблон диалогового окна. Производный класс `CFormView` для реализации пользовательского интерфейса, в зависимости от шаблона диалоговых окон.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Предоставляет форму непосредственно связана с объектом набора записей объекта доступа к данным (DAO). Все представления формы, например `CDaoRecordView` основан на шаблон диалогового окна.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Предоставляет форму непосредственно связана с объекта набора записей Open Database Connectivity (ODBC). Все представления формы, например `CRecordView` основан на шаблон диалогового окна.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Структура, содержащая сведения о задании печати или предварительного просмотра. Используемые печати архитектура [CView](../mfc/reference/cview-class.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

