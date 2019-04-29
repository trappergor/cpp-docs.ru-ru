---
title: Классы диалоговых окон
ms.date: 11/04/2016
f1_keywords:
- vc.classes.dialog
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
ms.openlocfilehash: 5747e4450816b803f97ad5ff6338b9e01ad41bca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394615"
---
# <a name="dialog-box-classes"></a>Классы диалоговых окон

Класс `CDialog` и его производные классы инкапсулируют функциональность диалогового окна. Так как диалоговое окно — это особый тип окна, `CDialog` является производным от `CWnd`. Производные классы диалоговое окно из `CDialog` или воспользуйтесь одним из классы общих диалоговых окон для стандартных диалоговых окон, таких как открытие или сохранение файла, печать, выбрав шрифт или цвет, инициации операции поиска и замены, или выполнения различных связанные с OLE операции.

[CDialog](../mfc/reference/cdialog-class.md)<br/>
Базовый класс для всех диалоговых окон, модальные и немодальные.

[CDataExchange](../mfc/reference/cdataexchange-class.md)<br/>
Предоставляет сведения о exchange и проверке данных по диалоговым окнам.

## <a name="common-dialogs"></a>Общие диалоговые окна

Эти классы диалоговых окон инкапсулировать общие диалоговые Windows. Они предоставляют реализации для использования сложных диалоговых окон.

[CCommonDialog](../mfc/reference/ccommondialog-class.md)<br/>
Базовый класс для всех окон.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
Предоставляет стандартное диалоговое окно открытия или сохранения файла.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для выбора цвета.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для выбора шрифта.

[Диалоговое окно CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для операции поиска и замены.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для печати файла.

[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)<br/>
Предоставляет таблицу свойств печати Windows.

[CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)<br/>
Инкапсулирует службы, предоставляемые Windows общее параметры страницы диалоговое окно с дополнительной поддержкой установки и изменения полей печати.

## <a name="ole-common-dialogs"></a>Общих диалоговых окон OLE

OLE добавляет несколько окон для Windows. Эти классы инкапсулируют OLE окон.

[COleDialog](../mfc/reference/coledialog-class.md)<br/>
Используется платформой для хранения реализаций для всех диалоговых окон OLE. Все классы диалоговых окон в категории пользовательского интерфейса являются производными от этого базового класса. `COleDialog` нельзя использовать напрямую.

[COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)<br/>
Отображаются диалоговом окне Вставка объекта в стандартный пользовательский интерфейс для вставки новых OLE связанных или внедренных элементов.

[COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)<br/>
Отображает Специальная вставка диалоговое окно, стандартный пользовательский интерфейс для реализации Специальная вставка команды.

[COleLinksDialog](../mfc/reference/colelinksdialog-class.md)<br/>
Отображает диалоговое окно Изменение связей, стандартный пользовательский интерфейс для изменения сведений о связанных элементах.

[COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)<br/>
Отображает диалоговое окно Смена значка, стандартный пользовательский интерфейс для изменения значка, связанного с OLE-внедренные или связанный элемент.

[COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)<br/>
Отображает диалоговое окно Convert, стандартный пользовательский интерфейс для преобразования элементов OLE из одного типа в другой.

[COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)<br/>
Инкапсулирует диалоговое окно общих свойств OLE Windows. Общие диалоговые окна свойств OLE предоставляют простой способ отображения и изменения свойств элемента документа OLE в соответствии со стандартами Windows.

[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)<br/>
Отображает диалоговое окно обновления стандартный пользовательский интерфейс для обновления всех ссылок в документе. Диалоговое окно содержит индикатор хода выполнения, чтобы указать, насколько близко процедуры обновления является до завершения.

[COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)<br/>
Отображает диалоговое окно Изменить источник, стандартный пользовательский интерфейс для изменения назначения или источника связи.

[COleBusyDialog](../mfc/reference/colebusydialog-class.md)<br/>
Отображает сервер занят диалоговые окна и сервер не отвечает, стандартный пользовательский интерфейс для обработки вызовов занят приложений. Обычно отображается автоматически [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) реализации.

## <a name="property-sheet-classes"></a>Классы вкладок свойств

Классы вкладок свойств позволяют вашим приложениям использовать страницы свойств, также известный как с вкладками диалоговые окна. Вкладки свойств — это эффективный способ упорядочить большое количество элементов управления в одном диалоговом окне.

[CPropertyPage](../mfc/reference/cpropertypage-class.md)<br/>
Предоставляет отдельные страницы в лист свойств. Наследуйте класс от `CPropertyPage` для каждой страницы Добавить вкладку свойств.

[CPropertySheet](../mfc/reference/cpropertysheet-class.md)<br/>
Предоставляет кадр для нескольких страниц свойств. Наследование класса листа свойств из `CPropertySheet` быстро реализовать ваши страницы свойств.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Отображает свойства OLE управления графическим интерфейсом, аналогичную диалоговое окно.

## <a name="html-based-dialog-classes"></a>Классы диалоговых окон на основе HTML

[CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)<br/>
Используется для создания диалоговых окон, которые реализуют их пользовательского интерфейса с помощью HTML, а не в диалоговое окно ресурсов.

[CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)<br/>
Последовательно отображает несколько HTML-страниц и обрабатывает события каждой страницы.

## <a name="related-classes"></a>Связанные классы

Эти классы не диалоговым окнам сам по себе, но они используют шаблоны диалоговых окон и иметь в большой степени поведение диалоговым окнам.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
Панель элементов управления, основанный на шаблон диалогового окна.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Представление прокрутки, макет которой определяется в шаблон диалогового окна. Наследуйте класс от `CFormView` для реализации пользовательского интерфейса, в зависимости от шаблона диалогового окна.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Предоставляет форму непосредственно связана с объектом набора записей объекта доступа к данным (DAO). Все представления формы, такие как `CDaoRecordView` основан на шаблон диалогового окна.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Предоставляет форму непосредственно связана с объект recordset Open Database Connectivity (ODBC). Все представления формы, такие как `CRecordView` основан на шаблон диалогового окна.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Структура, содержащая сведения о задании печати или предварительного просмотра. Используемые печати архитектура [CView](../mfc/reference/cview-class.md).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
