---
title: "CToolBarCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBarCtrl
- AFXCMN/CToolBarCtrl
- AFXCMN/CToolBarCtrl::CToolBarCtrl
- AFXCMN/CToolBarCtrl::AddBitmap
- AFXCMN/CToolBarCtrl::AddButtons
- AFXCMN/CToolBarCtrl::AddString
- AFXCMN/CToolBarCtrl::AddStrings
- AFXCMN/CToolBarCtrl::AutoSize
- AFXCMN/CToolBarCtrl::ChangeBitmap
- AFXCMN/CToolBarCtrl::CheckButton
- AFXCMN/CToolBarCtrl::CommandToIndex
- AFXCMN/CToolBarCtrl::Create
- AFXCMN/CToolBarCtrl::CreateEx
- AFXCMN/CToolBarCtrl::Customize
- AFXCMN/CToolBarCtrl::DeleteButton
- AFXCMN/CToolBarCtrl::EnableButton
- AFXCMN/CToolBarCtrl::GetAnchorHighlight
- AFXCMN/CToolBarCtrl::GetBitmap
- AFXCMN/CToolBarCtrl::GetBitmapFlags
- AFXCMN/CToolBarCtrl::GetButton
- AFXCMN/CToolBarCtrl::GetButtonCount
- AFXCMN/CToolBarCtrl::GetButtonInfo
- AFXCMN/CToolBarCtrl::GetButtonSize
- AFXCMN/CToolBarCtrl::GetColorScheme
- AFXCMN/CToolBarCtrl::GetDisabledImageList
- AFXCMN/CToolBarCtrl::GetDropTarget
- AFXCMN/CToolBarCtrl::GetExtendedStyle
- AFXCMN/CToolBarCtrl::GetHotImageList
- AFXCMN/CToolBarCtrl::GetHotItem
- AFXCMN/CToolBarCtrl::GetImageList
- AFXCMN/CToolBarCtrl::GetInsertMark
- AFXCMN/CToolBarCtrl::GetInsertMarkColor
- AFXCMN/CToolBarCtrl::GetItemRect
- AFXCMN/CToolBarCtrl::GetMaxSize
- AFXCMN/CToolBarCtrl::GetMaxTextRows
- AFXCMN/CToolBarCtrl::GetMetrics
- AFXCMN/CToolBarCtrl::GetPadding
- AFXCMN/CToolBarCtrl::GetPressedImageList
- AFXCMN/CToolBarCtrl::GetRect
- AFXCMN/CToolBarCtrl::GetRows
- AFXCMN/CToolBarCtrl::GetState
- AFXCMN/CToolBarCtrl::GetString
- AFXCMN/CToolBarCtrl::GetStyle
- AFXCMN/CToolBarCtrl::GetToolTips
- AFXCMN/CToolBarCtrl::HideButton
- AFXCMN/CToolBarCtrl::HitTest
- AFXCMN/CToolBarCtrl::Indeterminate
- AFXCMN/CToolBarCtrl::InsertButton
- AFXCMN/CToolBarCtrl::InsertMarkHitTest
- AFXCMN/CToolBarCtrl::IsButtonChecked
- AFXCMN/CToolBarCtrl::IsButtonEnabled
- AFXCMN/CToolBarCtrl::IsButtonHidden
- AFXCMN/CToolBarCtrl::IsButtonHighlighted
- AFXCMN/CToolBarCtrl::IsButtonIndeterminate
- AFXCMN/CToolBarCtrl::IsButtonPressed
- AFXCMN/CToolBarCtrl::LoadImages
- AFXCMN/CToolBarCtrl::MapAccelerator
- AFXCMN/CToolBarCtrl::MarkButton
- AFXCMN/CToolBarCtrl::MoveButton
- AFXCMN/CToolBarCtrl::PressButton
- AFXCMN/CToolBarCtrl::ReplaceBitmap
- AFXCMN/CToolBarCtrl::RestoreState
- AFXCMN/CToolBarCtrl::SaveState
- AFXCMN/CToolBarCtrl::SetAnchorHighlight
- AFXCMN/CToolBarCtrl::SetBitmapSize
- AFXCMN/CToolBarCtrl::SetButtonInfo
- AFXCMN/CToolBarCtrl::SetButtonSize
- AFXCMN/CToolBarCtrl::SetButtonStructSize
- AFXCMN/CToolBarCtrl::SetButtonWidth
- AFXCMN/CToolBarCtrl::SetCmdID
- AFXCMN/CToolBarCtrl::SetColorScheme
- AFXCMN/CToolBarCtrl::SetDisabledImageList
- AFXCMN/CToolBarCtrl::SetDrawTextFlags
- AFXCMN/CToolBarCtrl::SetExtendedStyle
- AFXCMN/CToolBarCtrl::SetHotImageList
- AFXCMN/CToolBarCtrl::SetHotItem
- AFXCMN/CToolBarCtrl::SetImageList
- AFXCMN/CToolBarCtrl::SetIndent
- AFXCMN/CToolBarCtrl::SetInsertMark
- AFXCMN/CToolBarCtrl::SetInsertMarkColor
- AFXCMN/CToolBarCtrl::SetMaxTextRows
- AFXCMN/CToolBarCtrl::SetMetrics
- AFXCMN/CToolBarCtrl::SetOwner
- AFXCMN/CToolBarCtrl::SetPadding
- AFXCMN/CToolBarCtrl::SetPressedImageList
- AFXCMN/CToolBarCtrl::SetRows
- AFXCMN/CToolBarCtrl::SetState
- AFXCMN/CToolBarCtrl::SetStyle
- AFXCMN/CToolBarCtrl::SetToolTips
- AFXCMN/CToolBarCtrl::SetWindowTheme
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class
- Windows common controls [C++], CToolBarCtrl
- toolbar controls [MFC], CToolBarCtrl class
- tool tips [C++], notifications
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: cd1b3fd923d4e523506f80ed413247ba4b3b58e5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="ctoolbarctrl-class"></a>CToolBarCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "панель инструментов" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CToolBarCtrl::CToolBarCtrl](#ctoolbarctrl)|Создает объект `CToolBarCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CToolBarCtrl::AddBitmap](#addbitmap)|Добавляет один или несколько растровые изображения кнопки в список изображений кнопок, доступных для элемента управления панели инструментов.|  
|[CToolBarCtrl::AddButtons](#addbuttons)|Добавляет одну или несколько кнопок в элемент управления toolbar.|  
|[CToolBarCtrl::AddString](#addstring)|Добавляет новую строку, переданный в качестве идентификатора ресурса панели инструментов внутренний список строк.|  
|[CToolBarCtrl::AddStrings](#addstrings)|Добавляет новую строку или строки, переданы в качестве указателя на буфер строк, разделенных null, панели инструментов внутренний список строк.|  
|[CToolBarCtrl::AutoSize](#autosize)|Изменяет размер элемента управления панели инструментов.|  
|[CToolBarCtrl::ChangeBitmap](#changebitmap)|Изменяет точечного рисунка для кнопки в текущий элемент управления панели инструментов.|  
|[CToolBarCtrl::CheckButton](#checkbutton)|Проверяет или очищает указанной кнопки элемента управления toolbar.|  
|[CToolBarCtrl::CommandToIndex](#commandtoindex)|Возвращает отсчитываемый от нуля индекс для кнопки, связанной с указанным идентификатором команды.|  
|[CToolBarCtrl::Create](#create)|Создает элемент управления панели инструментов и прикрепляет его к `CToolBarCtrl` объекта.|  
|[CToolBarCtrl::CreateEx](#createex)|Создает элемент управления панели инструментов с указанным расширенные стили Windows и прикрепляет его к `CToolBarCtrl` объекта.|  
|[CToolBarCtrl::Customize](#customize)|Отображает диалоговое окно Настройка панели инструментов.|  
|[CToolBarCtrl::DeleteButton](#deletebutton)|Удаление кнопки из панели инструментов.|  
|[CToolBarCtrl::EnableButton](#enablebutton)|Включает или отключает указанную кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::GetAnchorHighlight](#getanchorhighlight)|Получает выделение привязки, задание для панели инструментов.|  
|[CToolBarCtrl::GetBitmap](#getbitmap)|Извлекает индекс растровое изображение, связанное с кнопкой на панели инструментов.|  
|[CToolBarCtrl::GetBitmapFlags](#getbitmapflags)|Получает флаги, связанные с растровым изображением панели инструментов.|  
|[CToolBarCtrl::GetButton](#getbutton)|Получает сведения об указанной кнопки элемента управления toolbar.|  
|[CToolBarCtrl::GetButtonCount](#getbuttoncount)|Возвращает число кнопок элемента управления toolbar.|  
|[CToolBarCtrl::GetButtonInfo](#getbuttoninfo)|Возвращает сведения о кнопке на панели инструментов.|  
|[CToolBarCtrl::GetButtonSize](#getbuttonsize)|Извлекает текущий ширину и высоту кнопок панели инструментов, в пикселях.|  
|[CToolBarCtrl::GetColorScheme](#getcolorscheme)|Возвращает цветовую схему текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::GetDisabledImageList](#getdisabledimagelist)|Извлекает список изображений, для отображения отключены кнопок элемента управления toolbar.|  
|[CToolBarCtrl::GetDropTarget](#getdroptarget)|Извлекает [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейса для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetHotImageList](#gethotimagelist)|Извлекает список изображений, элемент управления панель инструментов используется для отображения кнопки «горячего». Кнопку в активном состоянии станет выделенным, когда указатель мыши находится над ним.|  
|[CToolBarCtrl::GetHotItem](#gethotitem)|Извлекает индекс горячей элемента на панели инструментов.|  
|[CToolBarCtrl::GetImageList](#getimagelist)|Извлекает список изображений, элемент управления панель инструментов используется для отображения кнопки в состоянии по умолчанию.|  
|[CToolBarCtrl::GetInsertMark](#getinsertmark)|Извлекает текущий метка вставки для панели инструментов.|  
|[CToolBarCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Получает цвет, используемый для рисования метка вставки для панели инструментов.|  
|[CToolBarCtrl::GetItemRect](#getitemrect)|Возвращает прямоугольник, ограничивающий кнопки в элементе управления панели инструментов.|  
|[CToolBarCtrl::GetMaxSize](#getmaxsize)|Получает общий размер всех кнопок видимым и в панели инструментов в качестве разделителей.|  
|[CToolBarCtrl::GetMaxTextRows](#getmaxtextrows)|Возвращает максимальное число строк текста, отображаемого на кнопке панели инструментов.|  
|[CToolBarCtrl::GetMetrics](#getmetrics)|Возвращает показатели элемента управления toolbar.|  
|[CToolBarCtrl::GetPadding](#getpadding)|Получает горизонтальный и вертикальный заполнение текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::GetPressedImageList](#getpressedimagelist)|Извлекает список изображений, текущего элемента управления панель инструментов используется для представления кнопки в нажатом состоянии.|  
|[CToolBarCtrl::GetRect](#getrect)|Возвращает ограничивающий прямоугольник для указанной кнопки.|  
|[CToolBarCtrl::GetRows](#getrows)|Возвращает число строк, кнопок, отображаемых на панели инструментов.|  
|[CToolBarCtrl::GetState](#getstate)|Извлекает сведения о состоянии от указанной кнопки в элементе управления панели инструментов, например, будь то включена, нажата или флажок установлен.|  
|[CToolBarCtrl::GetString](#getstring)|Извлекает строку, панели инструментов.|  
|[CToolBarCtrl::GetStyle](#getstyle)|Извлекает стили, которые в настоящее время для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetToolTips](#gettooltips)|Извлекает дескриптор управления всплывающей подсказки, если таковая имеется, связанный с элементом управления панели инструментов.|  
|[CToolBarCtrl::HideButton](#hidebutton)|Скрытие или отображение указанную кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::HitTest](#hittest)|Определяет, где находится точка элемента управления toolbar.|  
|[CToolBarCtrl::Indeterminate](#indeterminate)|Устанавливает или снимает неопределенное состояние указанной кнопки элемента управления toolbar (серый).|  
|[CToolBarCtrl::InsertButton](#insertbutton)|Вставляет кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::InsertMarkHitTest](#insertmarkhittest)|Извлекает сведения о метки вставки для точки на панели инструментов.|  
|[CToolBarCtrl::IsButtonChecked](#isbuttonchecked)|Указывает, установлен ли флажок указанную кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::IsButtonEnabled](#isbuttonenabled)|Указывает, включена ли кнопка, указанного в элементе управления панели инструментов.|  
|[CToolBarCtrl::IsButtonHidden](#isbuttonhidden)|Указывает, скрыт ли указанную кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::IsButtonHighlighted](#isbuttonhighlighted)|Для проверки состояния выделения кнопки панели инструментов.|  
|[CToolBarCtrl::IsButtonIndeterminate](#isbuttonindeterminate)|Сообщает, является ли состояние указанной кнопки элемента управления toolbar неопределенное (серый).|  
|[CToolBarCtrl::IsButtonPressed](#isbuttonpressed)|Указывает, нажата ли указанную кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::LoadImages](#loadimages)|Загружает растровых изображений в список изображений элемента управления панели инструментов.|  
|[CToolBarCtrl::MapAccelerator](#mapaccelerator)|Сопоставляет символ сочетаний клавиш для кнопки панели инструментов.|  
|[CToolBarCtrl::MarkButton](#markbutton)|Задает состояние выделения данной кнопки элемента управления toolbar.|  
|[CToolBarCtrl::MoveButton](#movebutton)|Перемещает кнопки из одного индекса в другую.|  
|[CToolBarCtrl::PressButton](#pressbutton)|Нажимает или отпускает указанную кнопку в элементе управления панели инструментов.|  
|[CToolBarCtrl::ReplaceBitmap](#replacebitmap)|Заменяет существующий растрового изображения в текущий элемент управления панели инструментов новое растровое изображение.|  
|[CToolBarCtrl::RestoreState](#restorestate)|Восстанавливает состояние элемента управления toolbar.|  
|[CToolBarCtrl::SaveState](#savestate)|Сохраняет состояние элемента управления toolbar.|  
|[CToolBarCtrl::SetAnchorHighlight](#setanchorhighlight)|Задает выделения привязки, задание для панели инструментов.|  
|[CToolBarCtrl::SetBitmapSize](#setbitmapsize)|Задает размер точечных рисунков для добавления элемента управления панели инструментов.|  
|[CToolBarCtrl::SetButtonInfo](#setbuttoninfo)|Задает сведения о существующую кнопку на панели инструментов.|  
|[CToolBarCtrl::SetButtonSize](#setbuttonsize)|Задает размер кнопки для добавления элемента управления панели инструментов.|  
|[CToolBarCtrl::SetButtonStructSize](#setbuttonstructsize)|Указывает размер `TBBUTTON` структуры.|  
|[CToolBarCtrl::SetButtonWidth](#setbuttonwidth)|Задает кнопку минимальную и максимальную ширину в элементе управления панели инструментов.|  
|[CToolBarCtrl::SetCmdID](#setcmdid)|Задает идентификатор команды, отправляемые окна-владельца, при нажатии кнопки указанного.|  
|[CToolBarCtrl::SetColorScheme](#setcolorscheme)|Задает цветовую схему текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::SetDisabledImageList](#setdisabledimagelist)|Задает список изображений, который будет использовать элемент управления панели инструментов для отображения отключены кнопок.|  
|[CToolBarCtrl::SetDrawTextFlags](#setdrawtextflags)|Задает флаги в функцию Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), который используется для рисования текста в указанном прямоугольнике, отформатированное согласно установке флагов.|  
|[CToolBarCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::SetHotImageList](#sethotimagelist)|Задает список изображений, используемый элементом управления панели инструментов для отображения кнопок «горячего».|  
|[CToolBarCtrl::SetHotItem](#sethotitem)|Задает горячей элемент на панели инструментов.|  
|[CToolBarCtrl::SetImageList](#setimagelist)|Задает список изображений, панели инструментов будет использовать для отображения кнопок, которые находятся в состоянии по умолчанию.|  
|[CToolBarCtrl::SetIndent](#setindent)|Задает отступ для первой кнопки элемента управления toolbar.|  
|[CToolBarCtrl::SetInsertMark](#setinsertmark)|Задает текущий метка вставки для панели инструментов.|  
|[CToolBarCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Задает цвет, используемый для рисования метка вставки для панели инструментов.|  
|[CToolBarCtrl::SetMaxTextRows](#setmaxtextrows)|Задает максимальное число строк текста, отображаемого на кнопке панели инструментов.|  
|[CToolBarCtrl::SetMetrics](#setmetrics)|Задает показатели элемента управления toolbar.|  
|[CToolBarCtrl::SetOwner](#setowner)|Задает окно, чтобы получать сообщения уведомления из элемента управления toolbar.|  
|[CToolBarCtrl::SetPadding](#setpadding)|Задает заполнение горизонтальные и вертикальные текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::SetPressedImageList](#setpressedimagelist)|Задает список изображений, текущего элемента управления панель инструментов используется для представления кнопки в нажатом состоянии.|  
|[CToolBarCtrl::SetRows](#setrows)|Задает количество строк, кнопок, отображаемых на панели инструментов.|  
|[CToolBarCtrl::SetState](#setstate)|Задает состояние для указанной кнопки элемента управления toolbar.|  
|[CToolBarCtrl::SetStyle](#setstyle)|Задает стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::SetToolTips](#settooltips)|Связывает всплывающая подсказка с элементом управления панели инструментов.|  
|[CToolBarCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль элемента управления toolbar.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент управления (и, следовательно, `CToolBarCtrl` класс) доступен только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Общего элемента управления панель инструментов Windows имеет прямоугольную дочернее окно, содержит одну или несколько кнопок. Эти кнопки можно отобразить растровое изображение и строку. Когда пользователь нажимает кнопку, он отправляет сообщение команды панели инструментов окна-владельца. Как правило кнопок на панели инструментов соответствуют элементам в меню приложения; они предоставляют более прямым способом для пользователя получить доступ к командам приложения.  
  
 `CToolBarCtrl`объекты содержат несколько важных внутренние структуры данных: список точечного рисунка для изображения кнопки или списка изображений, список строк метки кнопки и список `TBBUTTON` структуры, которые связать изображение и/или строка с позиции, стиль, состояние и ИД кнопки команды. Каждый из элементов этих структур данных ссылается отсчитываемый от нуля индекс. Прежде чем использовать `CToolBarCtrl` объекта, необходимо настроить эти структуры данных. Список строк может использоваться только для метки кнопок; не удается получить строки на панели инструментов.  
  
 Для использования `CToolBarCtrl` объекта, обычно выполняются следующие действия:  
  
1.  Создать `CToolBarCtrl` объекта.  
  
2.  Вызовите [создать](#create) для создания стандартного элемента управления панель инструментов Windows и присоединить его к `CToolBarCtrl` объекта. Указывает стиль панели инструментов с помощью стилей, таких как **TBSTYLE_TRANSPARENT** для прозрачной панели инструментов или **TBSTYLE_DROPDOWN** для панели инструментов, которая поддерживает кнопки раскрывающегося списка.  
  
3.  Определите способ кнопок на панели инструментов отображается:  
  
    -   Чтобы использовать растровые изображения для кнопок, добавить точечного рисунка для кнопки панели инструментов с помощью [AddBitmap](#addbitmap).  
  
    -   Чтобы использовать изображений, отображаемых из списка изображений для кнопок, укажите список изображений, вызвав [SetImageList](#setimagelist), [SetHotImageList](#sethotimagelist), или [SetDisabledImageList](#setdisabledimagelist).  
  
    -   Чтобы использовать строку подписи для кнопок, добавлять строки панели инструментов, вызвав [AddString](#addstring) и/или [AddStrings](#addstrings).  
  
4.  Добавить структуры кнопки панели инструментов с помощью [AddButtons](#addbuttons).  
  
5.  Если нужны всплывающие подсказки для кнопки панели инструментов в окно-владелец, не `CFrameWnd`, необходимо обработать **TTN_NEEDTEXT** сообщений в панели инструментов окна-владельца, как описано в [обработка уведомлений всплывающих совет](../../mfc/handling-tool-tip-notifications.md). Если родительское окно элемента панели инструментов является производным от `CFrameWnd`, всплывающие подсказки отображаются без дополнительных усилий от вас, так как `CFrameWnd` предоставляет обработчик по умолчанию.  
  
6.  Если вы хотите ваши пользователи, чтобы иметь возможность настроить панель инструментов, обрабатывать настройки уведомляющих сообщений в окно-владелец, как описано в [обработка уведомлений о настройке](../../mfc/handling-customization-notifications.md).  
  
 Можно использовать [SaveState](#savestate) для сохранения текущего состояния элемента управления toolbar в реестре и [RestoreState](#restorestate) для восстановления состояния на основе данных в реестре ранее. Помимо сохранения состояния панели инструментов между используется приложения, приложения обычно хранят состояние, прежде чем пользователь начинает настраивать панели инструментов, в случае, если пользователь хочет позднее восстановить в исходное состояние панели инструментов.  
  
## <a name="support-for-internet-explorer-version-40-and-later"></a>Поддержка Internet Explorer версии 4.0 и более поздние версии  
 Для поддержки функциональных возможностей, представленных в Internet Explorer версии 4.0 и более поздних версий, MFC предоставляет поддержки список изображений и прозрачным и плоский стили для элементов управления панели инструментов.  
  
 Прозрачные панели инструментов позволяет клиенту под панелью инструментов видны сквозь. Чтобы создать прозрачные панели инструментов, использовать оба **TBSTYLE_FLAT** и **TBSTYLE_TRANSPARENT** стили. Прозрачные панели инструментов компонентов отслеживание; то есть при перемещении указателя мыши на кнопку в активном состоянии на панели инструментов, изменяется внешний вид кнопки. Панели инструментов, созданные с только что **TBSTYLE_FLAT** стиль будет содержать кнопки, которые не являются прозрачными.  
  
 Поддержка список изображений позволяет гибкость управления, поведение по умолчанию, наиболее часто используемыми изображениями и отключенные изображения. Используйте [GetImageList](#getimagelist), [GetHotImageList](#gethotimagelist), и [GetDisabledImageList](#getdisabledimagelist) с помощью прозрачного панели инструментов для управления изображения в соответствии с его состояние:  
  
 Дополнительные сведения об использовании `CToolBarCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CToolBarCtrl](../../mfc/using-ctoolbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="addbitmap"></a>CToolBarCtrl::AddBitmap  
 Добавляет одно или несколько изображений кнопки в список изображений кнопок в панели инструментов.  
  
```  
int AddBitmap(
    int nNumButtons,  
    UINT nBitmapID);

 
int AddBitmap(
    int nNumButtons,  
    CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumButtons`  
 Количество изображений кнопки в битовой карте.  
  
 `nBitmapID`  
 Идентификатор ресурса точечного рисунка, который содержит изображение кнопки или изображения.  
  
 `pBitmap`  
 Указатель на `CBitmap` объект, содержащий изображение кнопки или изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого нового изображения в случае успешного выполнения; в противном случае - 1.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать Windows API [CreateMappedBitmap](http://msdn.microsoft.com/library/windows/desktop/bb787467) для сопоставления цветов перед добавлением растрового изображения на панель инструментов. Если передать указатель на **CBitMap** объекта, необходимо убедиться, что растрового изображения не удаляются до, после удаления панели инструментов.  
  
##  <a name="addbuttons"></a>CToolBarCtrl::AddButtons  
 Добавляет одну или несколько кнопок в элемент управления toolbar.  
  
```  
BOOL AddButtons(
    int nNumButtons,  
    LPTBBUTTON lpButtons);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumButtons`  
 Количество добавляемых кнопок.  
  
 `lpButtons`  
 Адрес массива `TBBUTTON` структур, содержащих сведения о кнопках для добавления. Должно быть одинаковое количество элементов в массиве, как кнопки, определяемое `nNumButtons`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpButtons` Указатель указывает на массив `TBBUTTON` структуры. Каждый `TBBUTTON` структуры связывают кнопки, добавляемый с стиль кнопки, состояние образа или строку, идентификатор команды и определенные пользователем данные:  
  
 `typedef struct _TBBUTTON {`  
  
 `int iBitmap;// zero-based index of button image`  
  
 `int idCommand;  // command to be sent when button pressed`  
  
 `BYTE fsState;   // button state--see below`  
  
 `BYTE fsStyle;   // button style--see below`  
  
 `DWORD dwData;   // application-defined value`  
  
 `int iString;// zero-based index of button label string`  
  
 `} TBBUTTON;`  
  
 Существуют следующие элементы.  
  
 **iBitmap**  
 Отсчитываемый от нуля индекс изображение кнопки, -1, если нет изображения для этой кнопки.  
  
 **idCommand**  
 Идентификатор команды, назначенный данной кнопке. Этот идентификатор отправляется **WM_COMMAND** сообщений при выборе кнопки. Если **fsStyle** член имеет `TBSTYLE_SEP` значение, этот элемент должен быть равен нулю.  
  
 **fsState**  
 Флаги состояния кнопок. Он может быть сочетанием значений, перечисленных ниже:  
  
- `TBSTATE_CHECKED`Эта кнопка имеет **TBSTYLE_CHECKED** стиля и нажат.  
  
- `TBSTATE_ENABLED`Кнопки, принимающее вводимые пользователем данные. Кнопка, которая не поддерживает это состояние не принимает ввод данных пользователем и отображается серым цветом.  
  
- `TBSTATE_HIDDEN`Кнопка не отображается и не может реагировать на действия пользователя.  
  
- `TBSTATE_INDETERMINATE`Кнопка отображается серым цветом.  
  
- `TBSTATE_PRESSED`Кнопка нажата.  
  
- `TBSTATE_WRAP`Кнопки ставится разрыв строки. Кнопки также должен иметь `TBSTATE_ENABLED` состояния.  
  
 **fsStyle**  
 Стиль кнопки. Он может быть сочетанием значений, перечисленных ниже:  
  
- `TBSTYLE_BUTTON`Создает стандартные клавиши.  
  
- `TBSTYLE_CHECK`Создает кнопку переключения между нажатой и ненажатое состояния при каждом щелчке по нему. Эта кнопка имеет другой цвет фона, когда он находится в нажатом состоянии.  
  
- `TBSTYLE_CHECKGROUP`Создает кнопку с галочкой, остается в нажатом положении, пока не нажата кнопка другой группы.  
  
- `TBSTYLE_GROUP`Создает кнопку, которая остается в нажатом положении, пока не нажата кнопка другой группы.  
  
- `TBSTYLE_SEP`Создает разделителя, предоставляя небольшой разрыв между группы кнопок. Кнопки, которая имеет этот стиль не реагировать на действия пользователя.  
  
 `dwData`  
 Определенные пользователем данные.  
  
 **iString**  
 Отсчитываемый от нуля индекс строки для использования в качестве кнопки метки, -1, если строка не для этой кнопки.  
  
 Изображения и/или строки, индекс которого можно предоставить необходимо ранее были добавлены к панели инструментов Список с помощью [AddBitmap](#addbitmap), [AddString](#addstring), и/или [AddStrings](#addstrings).  
  
##  <a name="addstring"></a>CToolBarCtrl::AddString  
 Добавляет новую строку, переданный в качестве идентификатора ресурса панели инструментов внутренний список строк.  
  
```  
int AddString(UINT nStringID);
```  
  
### <a name="parameters"></a>Параметры  
 *nStringID*  
 Идентификатор ресурса строкового ресурса, добавление в список строк элемента управления toolbar.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого новые строки, добавленной в случае успешного выполнения; в противном случае значение -1.  
  
##  <a name="addstrings"></a>CToolBarCtrl::AddStrings  
 Добавляет новую строку или строки в список строк, доступных для элемента управления панели инструментов.  
  
```  
int AddStrings(LPCTSTR lpszStrings);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszStrings*  
 Адрес буфера, который содержит один или несколько нулем строки для добавления в список строк на панели инструментов. Последняя строка должна заканчиваться точкой с двумя символами null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого новые строки, добавленной в случае успешного выполнения; в противном случае значение -1.  
  
### <a name="remarks"></a>Примечания  
 Символ null должны быть разделены строк в буфере. Необходимо убедиться, что последняя строка имеет два символы конца строки. Чтобы правильно отформатировать строковую константу, можно создать его как:  
  
 [!code-cpp[NVC_MFCControlLadenDialog #72](../../mfc/codesnippet/cpp/ctoolbarctrl-class_1.cpp)]  
  
 или  
  
 [!code-cpp[NVC_MFCControlLadenDialog #73](../../mfc/codesnippet/cpp/ctoolbarctrl-class_2.cpp)]  
  
 Не следует передавать `CString` объекта для этой функции, так как она не могут быть более одного символа null в `CString`.  
  
##  <a name="autosize"></a>CToolBarCtrl::AutoSize  
 Изменяет размер элемента управления панель инструментов полностью.  
  
```  
void AutoSize();
```  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует вызывать при изменении размера родительского окна, или при изменении размера панели инструментов (например, при установке размера кнопки или растрового изображения или добавить строки).  
  
##  <a name="changebitmap"></a>CToolBarCtrl::ChangeBitmap  
 Изменяет точечного рисунка для кнопки в текущий элемент управления панели инструментов.  
  
```  
BOOL ChangeBitmap(
    int idButton,   
    int iBitmap);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `idButton`|Идентификатор команды кнопки, которые должен получить новое растровое изображение.|  
|[in] `iBitmap`|Отсчитываемый от нуля индекс образа в список изображений для текущего элемента управления панели инструментов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 При успешном выполнении этого метода система отображает указанное изображение в указанную кнопку.  
  
 Этот метод отправляет [TB_CHANGEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787301) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода изменяется битовый массив **сохранения файла** кнопки к растровому изображению для **о** кнопки.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_3.cpp)]  
  
##  <a name="checkbutton"></a>CToolBarCtrl::CheckButton  
 Проверяет или очищает указанной кнопки элемента управления toolbar.  
  
```  
BOOL CheckButton(
    int nID,  
    BOOL bCheck = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки установите или снимите флажок.  
  
 *bПроверять обновления*  
 **Значение TRUE,** для проверки кнопки, **FALSE** снимите его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Когда переключатель похоже на нажатия. Если вы хотите изменить несколько состояний кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо него.  
  
##  <a name="commandtoindex"></a>CToolBarCtrl::CommandToIndex  
 Возвращает отсчитываемый от нуля индекс для кнопки, связанной с указанным идентификатором команды.  
  
```  
UINT CommandToIndex(UINT nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды, кнопка индекса вы хотите найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс кнопки, связанной с идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>CToolBarCtrl::Create  
 Создает элемент управления панели инструментов и прикрепляет его к `CToolBarCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления toolbar. Панели инструментов всегда должен иметь **WS_CHILD** стиля. Кроме того, можно указать любое сочетание стили окна и панели инструментов, как описано в разделе **примечания**.  
  
 `rect`  
 При необходимости указывает размер и положение элемента управления toolbar. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления панель инструментов. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления toolbar.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CToolBarCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления панели инструментов и прикрепляет его к `CToolBarCtrl` объекта. Применяются следующие стили окна для элемента управления панели инструментов.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
 В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] описание стили окна.  
  
 При необходимости примените сочетание [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Применить сочетание инструментов стили для элемента управления или кнопки сами. Стили, которые описаны в разделе [панели инструментов и стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb760439) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Чтобы использовать панель инструментов расширенные стили, вызовите [SetExtendedStyle](#setextendedstyle) после вызова метода **создать**. Чтобы создать панель инструментов с расширенные стили окна, вызовите [CToolBarCtrl::CreateEx](#createex) вместо **создать**.  
  
 Панели инструментов автоматически задает размер и положение окна инструментов. Высота основана на высоту кнопок на панели инструментов. Ширина равна таким же, как Ширина клиентской области родительского окна. `CCS_TOP` И `CCS_BOTTOM` определить стили, расположено ли вдоль верхней или нижней части клиентской области панели инструментов. По умолчанию имеет панель инструментов `CCS_TOP` стиля.  
  
##  <a name="createex"></a>CToolBarCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CToolBarCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль элемента управления toolbar. Панели инструментов всегда должен иметь **WS_CHILD** стиля. Кроме того, можно указать любое сочетание стили окна и панели инструментов, как описано в **примечания** раздел [создать](#create).  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**. **CreateEx** создает элемент управления с расширенные стили Windows, указанные для `dwExStyle`. Расширенные стили, определенные для элемента управления с помощью набора [SetExtendedStyle](#setextendedstyle). Например, использовать `CreateEx` задание стилей, таких как **WS_EX_CONTEXTHELP**, но использовать `SetExtendedStyle` задание стилей, таких как **TBSTYLE_EX_DRAWDDARROWS**. Дополнительные сведения см. в разделе стили, описанные в [расширенные стили панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760430) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ctoolbarctrl"></a>CToolBarCtrl::CToolBarCtrl  
 Создает объект `CToolBarCtrl`.  
  
```  
CToolBarCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [создать](#create) необходимо разрешить использование панели инструментов.  
  
##  <a name="customize"></a>CToolBarCtrl::Customize  
 Отображает диалоговое окно Настройка панели инструментов.  
  
```  
void Customize();
```  
  
### <a name="remarks"></a>Примечания  
 Это диалоговое окно предназначено позволяет пользователю выполнять настройку, добавляя и удаляя кнопки панели инструментов. Для поддержки настройки, управления панель инструментов родительское окно необходимо обрабатывать сообщения уведомления настройки, как описано в [обработка уведомлений о настройке](../../mfc/handling-customization-notifications.md). Панели инструментов необходимо также создать с помощью `CCS_ADJUSTABLE` стиля, как описано в [CToolBarCtrl::Create](#create).  
  
 Дополнительные сведения см. в статье базы знаний Q241850: PRB: вызов CToolBarCtrl::Customize не сохраняет видимым настройки диалогового окна.  
  
##  <a name="deletebutton"></a>CToolBarCtrl::DeleteButton  
 Удаление кнопки из панели инструментов.  
  
```  
BOOL DeleteButton(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки, чтобы удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablebutton"></a>CToolBarCtrl::EnableButton  
 Включает или отключает указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL EnableButton(
    int nID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды для включения или отключения кнопки.  
  
 `bEnable`  
 **Значение TRUE,** для включения кнопки. **FALSE** для выключения кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Когда кнопка включена, его можно нажата и проверки. Если вы хотите изменить несколько состояний кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо него.  
  
##  <a name="getanchorhighlight"></a>CToolBarCtrl::GetAnchorHighlight  
 Получает выделение привязки, задание для панели инструментов.  
  
```  
BOOL GetAnchorHighlight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, выделение привязка включена. Если значение равно нулю, выделение привязки отключен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787313), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbitmap"></a>CToolBarCtrl::GetBitmap  
 Извлекает индекс растровое изображение, связанное с кнопкой на панели инструментов.  
  
```  
int GetBitmap(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки — растрового изображения, индекс которого требуется извлечь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс битовой карты в случае успешного выполнения, или нуль, в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Реализует функции [TB_GETBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787315) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbitmapflags"></a>CToolBarCtrl::GetBitmapFlags  
 Получает флаги растровое изображение с панели инструментов.  
  
```  
UINT GetBitmapFlags() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** с **TBBF_LARGE** установлен флаг, если отображение может поддерживать растровые изображения панели инструментов, в противном случае снимите флажок.  
  
### <a name="remarks"></a>Примечания  
 Его следует вызывать после создания панели инструментов, но перед добавлением точечных рисунков для панели инструментов. Возвращаемое значение указывает, поддерживает ли отображение большие точечные рисунки. Если отображение поддерживает большие точечные рисунки и выберите их, вызовите [SetBitmapSize](#setbitmapsize) и [SetButtonSize](#setbuttonsize) перед добавлением большую битовую карту с помощью [AddBitmap](#addbitmap).  
  
##  <a name="getbutton"></a>CToolBarCtrl::GetButton  
 Получает сведения об указанной кнопки элемента управления toolbar.  
  
```  
BOOL GetButton(
    int nIndex,  
    LPTBBUTTON lpButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки, для которого требуется получить сведения.  
  
 `lpButton`  
 Адрес `TBBUTTON` структуру, для получения копии сведения о кнопке. В разделе [CToolBarCtrl::AddButtons](#addbuttons) сведения о `TBBUTTON` структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="getbuttoncount"></a>CToolBarCtrl::GetButtonCount  
 Возвращает число кнопок элемента управления toolbar.  
  
```  
int GetButtonCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число кнопок.  
  
##  <a name="getbuttoninfo"></a>CToolBarCtrl::GetButtonInfo  
 Возвращает сведения о кнопке на панели инструментов.  
  
```  
int GetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор кнопки.  
  
 `ptbbi`  
 Указатель на [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) структуру, которая получает сведения о кнопке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс кнопки в случае успешного выполнения; в противном случае значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787321), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbuttonsize"></a>CToolBarCtrl::GetButtonSize  
 Возвращает размер кнопки панели инструментов.  
  
```  
DWORD GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` значение, содержащее значения высоты и ширины в LOWORD и HIWORD, соответственно.  
  
##  <a name="getbuttontext"></a>CToolBarCtrl::GetButtonText  
 Получает отображаемый текст указанной кнопки на текущий элемент управления панели инструментов.  
  
```  
CString GetButtonText(int idButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `idButton`|Идентификатор для извлечения, отображаемый текст кнопки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/using-cstring.md) , содержащее отображаемый текст указанную кнопку.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETBUTTONTEXT](http://msdn.microsoft.com/library/windows/desktop/bb787325) сообщение, которое описано в Windows SDK.  
  
##  <a name="getcolorscheme"></a>CToolBarCtrl::GetColorScheme  
 Возвращает цветовую схему текущего элемента управления панели инструментов.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpColorScheme) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpColorScheme`|Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуру, которая получает сведения о схеме цвет. При возвращении данного метода, структура описывает цвет выделения и цвет тени панели инструментов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787327) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdisabledimagelist"></a>CToolBarCtrl::GetDisabledImageList  
 Извлекает список изображений, для отображения отключены кнопок элемента управления toolbar.  
  
```  
CImageList* GetDisabledImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, или **NULL** Если список отключенных изображений не задано.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787329), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Реализация MFC `GetDisabledImageList` использует `CImageList` образы объект, содержащий кнопки панели инструментов, вместо того чтобы дескриптор списка изображений.  
  
##  <a name="getdroptarget"></a>CToolBarCtrl::GetDropTarget  
 Извлекает [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейса для элемента управления панели инструментов.  
  
```  
HRESULT GetDropTarget(IDropTarget** ppDropTarget) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppDropTarget`  
 Указатель на [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) указатель на интерфейс. При возникновении ошибки **NULL** указатель помещается в этот адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `HRESULT` значение указывает на успешное или неуспешное выполнение операции.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787343), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getextendedstyle"></a>CToolBarCtrl::GetExtendedStyle  
 Извлекает расширенные стили для элемента управления панели инструментов.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` , представляющий расширенные стили, которые в настоящее время для элемента управления toolbar. Список стилей см. в разделе [расширенные стили панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760430)в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787331), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gethotimagelist"></a>CToolBarCtrl::GetHotImageList  
 Извлекает список изображений, элемент управления панель инструментов используется для отображения кнопки «горячего». Кнопку в активном состоянии станет выделенным, когда указатель мыши находится над ним.  
  
```  
CImageList* GetHotImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, или **NULL** Если список отключенных изображений не задано.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787334), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Кнопку в активном состоянии станет выделенным, когда указатель мыши находится над ним.  
  
##  <a name="gethotitem"></a>CToolBarCtrl::GetHotItem  
 Извлекает индекс горячей элемента на панели инструментов.  
  
```  
int GetHotItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента горячей на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787336), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getimagelist"></a>CToolBarCtrl::GetImageList  
 Извлекает список изображений, элемент управления панель инструментов используется для отображения кнопки в состоянии по умолчанию.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, или **NULL** Если список изображений не задано.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787337), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getinsertmark"></a>CToolBarCtrl::GetInsertMark  
 Извлекает текущий метка вставки для панели инструментов.  
  
```  
void GetInsertMark(TBINSERTMARK* ptbim) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ptbim`  
 Указатель на [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) структуру, которая получает метка вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787338), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getinsertmarkcolor"></a>CToolBarCtrl::GetInsertMarkColor  
 Получает цвет, используемый для рисования метка вставки для панели инструментов.  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее текущий цвет метки вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787339), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemrect"></a>CToolBarCtrl::GetItemRect  
 Возвращает прямоугольник, ограничивающий кнопки в элементе управления панели инструментов.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки, для которого требуется получить сведения.  
  
 `lpRect`  
 Адрес [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта, получающая координаты ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не извлекает ограничивающий прямоугольник для кнопки, состояние которого задано значение `TBSTATE_HIDDEN`.  
  
##  <a name="getmaxsize"></a>CToolBarCtrl::GetMaxSize  
 Получает общий размер всех кнопок видимым и в панели инструментов в качестве разделителей.  
  
```  
BOOL GetMaxSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pSize`  
 Указатель на [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуру, которая получает размер элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETMAXSIZE](http://msdn.microsoft.com/library/windows/desktop/bb787341), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmaxtextrows"></a>CToolBarCtrl::GetMaxTextRows  
 Возвращает максимальное число строк текста, отображаемого на кнопке панели инструментов.  
  
```  
int GetMaxTextRows() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число строк текста, отображаемого на кнопке панели инструментов.  
  
##  <a name="getmetrics"></a>CToolBarCtrl::GetMetrics  
 Возвращает показатели `CToolBarCtrl` объекта.  
  
```  
void GetMetrics(LPTBMETRICS ptbm) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ptbm`  
 Указатель на [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) структуры `CToolBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TB_GETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787342) сообщения, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getpadding"></a>CToolBarCtrl::GetPadding  
 Получает горизонтальный и вертикальный заполнение текущего элемента управления панели инструментов.  
  
```  
BOOL GetPadding(
    int* pnHorzPadding,   
    int* pnVertPadding) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pnHorzPadding`|Целое число, получающий горизонтальный отступ элемента управления панели инструментов, в пикселях.|  
|[выходной] `pnVertPadding`|Целое число, Получает вертикальный отступ элемента управления панели инструментов, в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787344) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getpressedimagelist"></a>CToolBarCtrl::GetPressedImageList  
 Извлекает список изображений, текущего элемента управления панель инструментов используется для представления кнопки в нажатом состоянии.  
  
```  
CImageList* GetPressedImageList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий список изображений для текущего элемента управления, или `NULL` Если такой список изображений не задано.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787345) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getrect"></a>CToolBarCtrl::GetRect  
 Возвращает ограничивающий прямоугольник для указанной кнопки.  
  
```  
BOOL GetRect(
    int nID,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор кнопки.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры получать сведения ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если успешно; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb787346), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getrows"></a>CToolBarCtrl::GetRows  
 Возвращает число строк, кнопок, отображаемых элементом управления панели инструментов.  
  
```  
int GetRows() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк, кнопок, отображаемых на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Следует заметить, что количество строк всегда один, если не был создан панели инструментов с `TBSTYLE_WRAPABLE` стиля.  
  
##  <a name="getstate"></a>CToolBarCtrl::GetState  
 Извлекает сведения о состоянии от указанной кнопки в элементе управления панели инструментов, например, будь то включена, нажата или флажок установлен.  
  
```  
int GetState(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, для которого требуется получить сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сведения о состоянии кнопки в случае успешного выполнения или - 1 в противном случае. Сведения о состоянии кнопка может быть сочетанием значений, перечисленных в [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="remarks"></a>Примечания  
 Эта функция особенно полезна в том случае, если вы хотите получить более одного из состояния кнопки. Получить только одно состояние с помощью одного из следующих функций-членов: [IsButtonEnabled](#isbuttonenabled), [IsButtonChecked](#isbuttonchecked), [IsButtonPressed](#isbuttonpressed), [IsButtonHidden](#isbuttonhidden), или [IsButtonIndeterminate](#isbuttonindeterminate). Тем не менее `GetState` функция-член является единственным способом обнаружения `TBSTATE_WRAP` кнопку состояние.  
  
##  <a name="getstring"></a>CToolBarCtrl::GetString  
 Извлекает строку, панели инструментов.  
  
```  
int GetString(
    int nString,  
    LPTSTR lpstrString,  
    int cchMaxLen) const;  
  
int GetString(
    int nString,  
    CString& str) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nString*  
 Индекс строки.  
  
 *lpstrString*  
 Указатель на буфер, применяемое для возврата строки.  
  
 *cchMaxLen*  
 Длина буфера в байтах.  
  
 `str`  
 Строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки, в случае успешного выполнения, -1, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETSTRING](http://msdn.microsoft.com/library/windows/desktop/bb787349), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getstyle"></a>CToolBarCtrl::GetStyle  
 Получает стили, примененные к элементу управления панели инструментов.  
  
```  
DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` содержащий сочетание [стили элемента управления панель инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettooltips"></a>CToolBarCtrl::GetToolTips  
 Извлекает дескриптор управления всплывающей подсказки, если таковая имеется, связанный с элементом управления панели инструментов.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта, связанного с этой панели инструментов или **NULL** Если панель инструментов не связан всплывающая подсказка.  
  
### <a name="remarks"></a>Примечания  
 Поскольку элемент управления панели инструментов обычно создает и обслуживает собственный всплывающая подсказка, большинство программ не требуется для вызова этой функции.  
  
##  <a name="hittest"></a>CToolBarCtrl::HitTest  
 Определяет, где находится точка элемента управления toolbar.  
  
```  
int HitTest(LPPOINT ppt) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppt`  
 Указатель на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, содержащую Координата по оси x для проверки нажатия в **x** член и y координата попадание тестирования в **y** член. Координаты указываются относительно клиентской области панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, указывающее, расположение точки на панели инструментов. Если значение равно 0 или положительное значение, возвращаемое значение представляет отсчитываемый от нуля индекс элемента nonseparator, в которой находится точка.  
  
 Если возвращаемое значение является отрицательным, точке выйдет за пределы кнопки. Абсолютное значение, возвращаемое значение — это индекс элемента разделителя или ближайшего элемента nonseparator.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787360), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="hidebutton"></a>CToolBarCtrl::HideButton  
 Скрытие или отображение указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL HideButton(
    int nID,  
    BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, чтобы скрыть или отобразить.  
  
 `bHide`  
 **Значение TRUE,** для скрытия кнопки, **FALSE** он будет отображаться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите изменить несколько состояний кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо него.  
  
##  <a name="indeterminate"></a>CToolBarCtrl::Indeterminate  
 Устанавливает или снимает неопределенное состояние указанной кнопки элемента управления toolbar.  
  
```  
BOOL Indeterminate(
    int nID,  
    BOOL bIndeterminate = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды, неопределенное состояние которой нужно установить или очистить кнопки.  
  
 *bIndeterminate*  
 **Значение TRUE,** неопределенное состояние для указанной кнопки **FALSE** снимите его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Неопределенное кнопки отображаются серым цветом, такие как способ полужирным кнопку на панели инструментов Текстовый процессор будет выглядеть при выбранного текста содержит символы полужирным и обычным. Если вы хотите изменить несколько состояний кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо него.  
  
##  <a name="insertbutton"></a>CToolBarCtrl::InsertButton  
 Вставляет кнопку в элементе управления панели инструментов.  
  
```  
BOOL InsertButton(
    int nIndex,  
    LPTBBUTTON lpButton);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки. Эта функция вставляет новую кнопку слева от этой кнопки.  
  
 `lpButton`  
 Адрес `TBBUTTON` структуру, содержащую сведения о кнопке для вставки. В разделе [CToolBarCtrl::AddButtons](#addbuttons) описание `TBBUTTON` структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Изображения и/или строки, индекс которого можно предоставить необходимо ранее были добавлены к панели инструментов Список с помощью [AddBitmap](#addbitmap), [AddString](#addstring), и/или [AddStrings](#addstrings).  
  
##  <a name="insertmarkhittest"></a>CToolBarCtrl::InsertMarkHitTest  
 Извлекает сведения о метки вставки для точки на панели инструментов.  
  
```  
BOOL InsertMarkHitTest(
    LPPOINT ppt,  
    LPTBINSERTMARK ptbim) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppt`  
 Указатель на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, содержащую нажатия координаты относительно клиентской области панели инструментов.  
  
 `ptbim`  
 Указатель на [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) структуру, которая получает сведения о метки вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787367), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isbuttonchecked"></a>CToolBarCtrl::IsButtonChecked  
 Определяет, проверяется ли указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL IsButtonChecked(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если она нажата; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить более одного состояния кнопки.  
  
##  <a name="isbuttonenabled"></a>CToolBarCtrl::IsButtonEnabled  
 Определяет, включена ли кнопка, указанного в элементе управления панели инструментов.  
  
```  
BOOL IsButtonEnabled(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка доступна; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить более одного состояния кнопки.  
  
##  <a name="isbuttonhidden"></a>CToolBarCtrl::IsButtonHidden  
 Определяет, является ли скрытым указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL IsButtonHidden(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка является скрытой; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить более одного состояния кнопки.  
  
##  <a name="isbuttonhighlighted"></a>CToolBarCtrl::IsButtonHighlighted  
 Для проверки состояния выделения кнопки панели инструментов.  
  
```  
BOOL IsButtonHighlighted(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды для кнопки панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положительное целое число, если выделена кнопка, 0, если кнопке гаснет или -1, если произошла ошибка возникает.  
  
##  <a name="isbuttonindeterminate"></a>CToolBarCtrl::IsButtonIndeterminate  
 Определяет, является ли неопределенное указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL IsButtonIndeterminate(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положительное целое число, если не определен, кнопки нуль, если кнопка не определен или -1, если ошибка возникает.  
  
### <a name="remarks"></a>Примечания  
 Неопределенное кнопки отображаются серым цветом, такие, как выглядит способом полужирным кнопку на панели инструментов текстового редактора, когда выбранный текст содержит символы полужирным и обычным. Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить более одного состояния кнопки.  
  
##  <a name="isbuttonpressed"></a>CToolBarCtrl::IsButtonPressed  
 Определяет, нажата ли указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL IsButtonPressed(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, при нажатии кнопки, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить более одного состояния кнопки.  
  
##  <a name="loadimages"></a>CToolBarCtrl::LoadImages  
 Загружает растровых изображений в список изображений элемента управления панели инструментов.  
  
```  
void LoadImages(
    int iBitmapID,  
    HINSTANCE hinst);
```  
  
### <a name="parameters"></a>Параметры  
 *iBitmapID*  
 Идентификатор точечного рисунка, который содержит изображения для загрузки. Для определения ресурса точечного рисунка, установите этот параметр, чтобы идентификатор ресурса точечного рисунка и установить `hInst` для **NULL**. Ресурс растрового изображения будут добавлены в список изображений как единый образ. Можно добавить стандартные, определяемые системой растровые изображения, установив *hinst* для **HINST_COMMCTRL** и этот параметр в один из следующих идентификаторов:  
  
|Идентификатор точечного рисунка|Описание|  
|---------------|-----------------|  
|IDB_HIST_LARGE_COLOR|Растровые изображения Explorer большого размера|  
|IDB_HIST_SMALL_COLOR|Обозреватель растровых изображений небольшого размера|  
|IDB_STD_LARGE_COLOR|Стандартная растровые изображения большого размера|  
|IDB_STD_SMALL_COLOR|Стандартная растровых изображений небольшого размера|  
|IDB_VIEW_LARGE_COLOR|Растровые изображения представления большого размера|  
|IDB_VIEW_SMALL_COLOR|Представление растровых изображений небольшого размера|  
  
 *hinst*  
 Дескриптор экземпляра программы вызывающему приложению. Этот параметр может иметь **HINST_COMMCTRL** для загрузки списка стандартный образ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_LOADIMAGES](http://msdn.microsoft.com/library/windows/desktop/bb787381), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="mapaccelerator"></a>CToolBarCtrl::MapAccelerator  
 Сопоставляет символ сочетаний клавиш для кнопки панели инструментов.  
  
```  
BOOL MapAccelerator(
    TCHAR chAccel,  
    UINT* pIDBtn);
```  
  
### <a name="parameters"></a>Параметры  
 `chAccel`  
 Символ сочетаний клавиш для сопоставления. Этот символ имеет тот же знак, подчеркнутый текст кнопки.  
  
 *pIDBtn*  
 Указатель на **UINT** , получающий идентификатор команды кнопки, которая соответствует сочетания клавиш, указанные в `chAccel`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_MAPACCELERATOR](http://msdn.microsoft.com/library/windows/desktop/bb787383), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="markbutton"></a>CToolBarCtrl::MarkButton  
 Задает состояние выделения данной кнопки элемента управления toolbar.  
  
```  
BOOL MarkButton(
    int nID,  
    BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор кнопки.  
  
 `fHighlight`  
 Указывает состояние выделения требуется задать. По умолчанию **TRUE**. Если значение **FALSE**, кнопки устанавливается в состояние по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_MARKBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787385), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="movebutton"></a>CToolBarCtrl::MoveButton  
 Перемещает кнопки из одного индекса в другую.  
  
```  
BOOL MoveButton(
    UINT nOldPos,  
    UINT nNewPos);
```  
  
### <a name="parameters"></a>Параметры  
 *nOldPos*  
 Отсчитываемый от нуля индекс кнопки для перемещения.  
  
 *nNewPos*  
 Отсчитываемый от нуля индекс назначения кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_MOVEBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787387), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="pressbutton"></a>CToolBarCtrl::PressButton  
 Нажимает или отпускает указанную кнопку в элементе управления панели инструментов.  
  
```  
BOOL PressButton(int nID, BOOL bPress = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды кнопки сочетание клавиш или выпуска.  
  
 [in] `bPress`  
 `true`сочетания клавиш указанной кнопки. `false` освободить указанную кнопку. Значение по умолчанию — `true`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод выполнен успешно; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите изменить несколько состояний кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо него.  
  
 Этот метод отправляет [TB_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787389) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="replacebitmap"></a>CToolBarCtrl::ReplaceBitmap  
 Заменяет существующий растрового изображения в текущий элемент управления панели инструментов новое растровое изображение.  
  
```  
BOOL ReplaceBitmap(LPTBREPLACEBITMAP pReplaceBitmap);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pReplaceBitmap`|Указатель на [TBREPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb760484) структура, описывающая точечный рисунок заменяемый и новое растровое изображение.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_REPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787391) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода заменяет точечный рисунок для панели инструментов Стандартная различных растрового изображения.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_4.cpp)]  
  
##  <a name="restorestate"></a>CToolBarCtrl::RestoreState  
 Восстанавливает состояние панели инструментов из расположения в реестре, указанный параметрами.  
  
```  
void RestoreState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Параметры  
 `hKeyRoot`  
 Идентифицирует открытый ключ в реестре или любой из следующих предопределенных зарезервированных дескриптор:  
  
- **РАЗДЕЛ HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Указывает нулем строка, содержащая имя раздела, с которым связано значение. Этот параметр может иметь значение null или указатель на пустую строку. Если параметр **NULL**, будут добавлены в ключ, обозначенный `hKeyRoot` параметра.  
  
 `lpszValueName`  
 Указывает строку, содержащую имя извлекаемого значения. Если значение с таким именем не существует в ключе, функция добавляет его ключ.  
  
##  <a name="savestate"></a>CToolBarCtrl::SaveState  
 Сохраняет состояние элемента управления панели инструментов в расположении в реестре, указанный параметрами.  
  
```  
void SaveState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Параметры  
 `hKeyRoot`  
 Идентифицирует открытый ключ в реестре или любой из следующих предопределенных зарезервированных дескриптор:  
  
- **РАЗДЕЛ HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Указывает нулем строка, содержащая имя раздела, с которым связано значение. Этот параметр может иметь значение null или указатель на пустую строку. Если параметр **NULL**, будут добавлены в ключ, обозначенный `hKeyRoot` параметра.  
  
 `lpszValueName`  
 Указывает строку, содержащую имя, значение которого требуется задать. Если значение с таким именем не существует в ключе, функция добавляет его ключ.  
  
##  <a name="setanchorhighlight"></a>CToolBarCtrl::SetAnchorHighlight  
 Задает выделения привязки, задание для панели инструментов.  
  
```  
BOOL SetAnchorHighlight(BOOL fAnchor = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `fAnchor`  
 Указывает, если выделение привязки включен или отключен. Если это значение не равно нулю, выделение привязки будет включена. Если это значение равно нулю, будут отключены выделение привязки  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущая Настройка привязки. Если выделение было включено, это значение не равно нулю. Если выделение не включена, это значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [TB_SETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787396), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbitmapsize"></a>CToolBarCtrl::SetBitmapSize  
 Задает размер фактическое точечных рисунков для добавления элемента управления панели инструментов.  
  
```  
BOOL SetBitmapSize(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Ширина и высота в пикселях точечных рисунков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию необходимо вызывать только перед добавлением любой растровые изображения панели инструментов. Если приложение явно не задано размера битовой карты, то по умолчанию до 15, 16 пикселей.  
  
##  <a name="setbuttoninfo"></a>CToolBarCtrl::SetButtonInfo  
 Задает сведения о существующую кнопку на панели инструментов.  
  
```  
BOOL SetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор кнопки.  
  
 `ptbbi`  
 Указатель на [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) структуру, которая получает сведения о кнопке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция-член реализует поведение сообщения Win32 [TB_SETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787413), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbuttonsize"></a>CToolBarCtrl::SetButtonSize  
 Задает размер кнопок в панели инструментов.  
  
```  
BOOL SetButtonSize(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Ширина и высота в пикселях кнопок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Размер кнопки всегда должен быть не меньше размера битовой карты, которые он помещает. Эту функцию необходимо вызывать только перед добавлением любой растровые изображения панели инструментов. Если приложение явно не задает размер кнопки, то по умолчанию 24 x 22 пикселов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CToolBar::GetToolBarCtrl](../../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
##  <a name="setbuttonstructsize"></a>CToolBarCtrl::SetButtonStructSize  
 Указывает размер `TBBUTTON` структуры.  
  
```  
void SetButtonStructSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Размер в байтах для объекта `TBBUTTON` структуры.  
  
### <a name="remarks"></a>Примечания  
 Если требуется для хранения дополнительных данных в `TBBUTTON` структуры, можно либо создать новую структуру из `TBBUTTON`, добавление элементов вам требуются или создать новую структуру, содержащую `TBBUTTON` структуру, что ее первого элемента. Затем необходимо вызвать эту функцию, чтобы определить размер новой структуры элемента управления toolbar.  
  
 В разделе [CToolBarCtrl::AddButtons](#addbuttons) Дополнительные сведения о `TBBUTTON` структуры.  
  
##  <a name="setbuttonwidth"></a>CToolBarCtrl::SetButtonWidth  
 Задает кнопку минимальную и максимальную ширину в элементе управления панели инструментов.  
  
```  
BOOL SetButtonWidth(
    int cxMin,  
    int cxMax);
```  
  
### <a name="parameters"></a>Параметры  
 `cxMin`  
 Кнопка Минимальная ширина в пикселях. Кнопки панели инструментов никогда не будет уже, чем это значение.  
  
 *cxMax*  
 Максимальное число кнопок ширина в пикселях. Текст кнопки слишком велик, элемент управления отображает с точки с многоточием.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETBUTTONWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb787417), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcmdid"></a>CToolBarCtrl::SetCmdID  
 Задает идентификатор команды, отправляемое окна-владельца, при нажатии указанной кнопки.  
  
```  
BOOL SetCmdID(
    int nIndex,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки для команды, идентификатор которого задается.  
  
 `nID`  
 Идентификатор команды, значение выделенной кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение, если успешно; в противном случае значение равно нулю.  
  
##  <a name="setcolorscheme"></a>CToolBarCtrl::SetColorScheme  
 Задает цветовую схему текущего элемента управления панели инструментов.  
  
```  
void SetColorScheme(const COLORSCHEME* lpColorScheme);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `lpColorScheme`|Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структура, описывающая цвет выделения и цвет тени панели инструментов.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод не оказывает влияния [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] задать визуальную тему.  
  
 Этот метод отправляет [TB_SETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787421) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается цветовой схемы для текущего элемента управления панели инструментов. В примере кода делает синий левую и верхнюю границы кнопок средство, красный и краями справа и снизу. Когда пользователь нажимает кнопку, красный края кнопки синим цветом и синий краев красным цветом.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_5.cpp)]  
  
##  <a name="setdisabledimagelist"></a>CToolBarCtrl::SetDisabledImageList  
 Задает список изображений, который будет использовать элемент управления панели инструментов для отображения отключены кнопок.  
  
```  
CImageList* SetDisabledImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения для использования с элементом управления для отображения неактивных изображения кнопки панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, который ранее использовался элементом управления панели инструментов для изображения кнопки отображения отключены.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787423), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Реализация MFC `SetDisabledImageList` использует `CImageList` образы объект, содержащий отключенной кнопки панели инструментов, вместо того чтобы дескриптор списка изображений.  
  
##  <a name="setdrawtextflags"></a>CToolBarCtrl::SetDrawTextFlags  
 Задает флаги в функцию Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), который используется для рисования текста в указанном прямоугольнике, отформатированное согласно установке флагов.  
  
```  
DWORD SetDrawTextFlags(
    DWORD dwMask,  
    DWORD dwDTFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMask`  
 Сочетание одного или нескольких флагов DT_, указанные в функции Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), которое указывает, что биты в `dwDTFlags` будет использоваться при рисовании текста.  
  
 `dwDTFlags`  
 Сочетание одного или нескольких флагов DT_, указанные в функции Win32 `DrawText`, указывающие, каким образом будет отображаться на кнопке отображается надпись. Это значение передается `DrawText` при рисуется текст кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` содержащий Рисование флаги в текст.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETDRAWTEXTFLAGS](http://msdn.microsoft.com/library/windows/desktop/bb787425), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Эта функция-член задает флаги в функцию Win32 `DrawText`, который рисует текст в указанном прямоугольнике, отформатированное согласно установке флагов.  
  
##  <a name="setextendedstyle"></a>CToolBarCtrl::SetExtendedStyle  
 Задает расширенные стили для элемента управления панели инструментов.  
  
```  
DWORD SetExtendedStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Значение, указывающее новые расширенные стили. Этот параметр может быть сочетанием панели инструментов расширенных стилей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` , представляющий предыдущий расширенные стили. Список стилей см. в разделе [расширенные стили панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760430)в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787427), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sethotimagelist"></a>CToolBarCtrl::SetHotImageList  
 Задает список изображений, используемый элементом управления панели инструментов для отображения кнопок «горячего».  
  
```  
CImageList* SetHotImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения для использования с элементом управления панели инструментов для отображения изображений кнопку в активном состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, который ранее использовался в панели инструментов для отображения изображений кнопку в активном состоянии.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787429), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Реализация MFC `SetHotImageList` использует `CImageList` образы объект, содержащий кнопку панели инструментов в активном состоянии, а не дескриптор списка изображений. Кнопку в активном состоянии станет выделенным, когда указатель находится над ним.  
  
##  <a name="sethotitem"></a>CToolBarCtrl::SetHotItem  
 Задает горячей элемент на панели инструментов.  
  
```  
int SetHotItem(int nHot);
```  
  
### <a name="parameters"></a>Параметры  
 *nHot*  
 Отсчитываемый от нуля индекс элемента, который будет осуществляться горячей. Если это значение равно -1, ни один из элементов не горячей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс предыдущего элемента горячей или -1, если не было горячей элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787431), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setimagelist"></a>CToolBarCtrl::SetImageList  
 Задает список изображений, панели инструментов будет использовать для отображения кнопок, которые находятся в состоянии по умолчанию.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения для использования с элементом управления панели инструментов для отображения изображения кнопки в состоянии по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, который ранее использовался элементом управления панели инструментов для отображения изображения кнопки в состоянии по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787433), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Реализация MFC `SetImageList` использует `CImageList` образы объект, содержащий кнопки панели инструментов, вместо того чтобы дескриптор списка изображений.  
  
##  <a name="setindent"></a>CToolBarCtrl::SetIndent  
 Задает отступ для первой кнопки элемента управления toolbar.  
  
```  
BOOL SetIndent(int iIndent);
```  
  
### <a name="parameters"></a>Параметры  
 *iIndent*  
 Значение, указывающее отступ в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="setinsertmark"></a>CToolBarCtrl::SetInsertMark  
 Задает текущий метка вставки для панели инструментов.  
  
```  
void SetInsertMark(TBINSERTMARK* ptbim);
```  
  
### <a name="parameters"></a>Параметры  
 `ptbim`  
 Указатель на [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) структуру, содержащую знак вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787437), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setinsertmarkcolor"></a>CToolBarCtrl::SetInsertMarkColor  
 Задает цвет, используемый для рисования метка вставки для панели инструментов.  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Параметры  
 `clrNew`  
 Объект **COLORREF** значение, содержащее новый цвет метки вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее предыдущий цвет метки вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setmaxtextrows"></a>CToolBarCtrl::SetMaxTextRows  
 Задает максимальное число строк текста, отображаемого на кнопке панели инструментов.  
  
```  
BOOL SetMaxTextRows(int iMaxRows);
```  
  
### <a name="parameters"></a>Параметры  
 *iMaxRows*  
 Максимальное число строк, которые требуется задать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="setmetrics"></a>CToolBarCtrl::SetMetrics  
 Задает показатели `CToolBarCtrl` объекта.  
  
```  
void SetMetrics(LPTBMETRICS ptbm);
```  
  
### <a name="parameters"></a>Параметры  
 `ptbm`  
 Указатель на [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) структуры `CToolBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TB_SETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787446) сообщения, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setowner"></a>CToolBarCtrl::SetOwner  
 Задает для элемента управления панели инструментов окна-владельца.  
  
```  
void SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на `CWnd` или `CWnd`-производный объект, который будет нового окна-владельца для элемента управления toolbar.  
  
### <a name="remarks"></a>Примечания  
 Окно-владелец — это окно, получающий уведомления от панели инструментов.  
  
##  <a name="setpadding"></a>CToolBarCtrl::SetPadding  
 Задает заполнение горизонтальные и вертикальные текущего элемента управления панели инструментов.  
  
```  
DWORD SetPadding(
    int nHorzPadding,   
    int nVertPadding);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nHorzPadding`|Задает горизонтальный отступ элемента управления панели инструментов, в пикселях.|  
|[in] `nVertPadding`|Задает вертикальный отступ элемента управления панели инструментов, в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` которого младшее слово содержится значение горизонтальный отступ и которого старшее слово содержится значение вертикальный отступ. Заполнение значений измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_SETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787448) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает заполнение горизонтальные и вертикальные текущего элемента управления панели инструментов до 20 пикселей.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_6.cpp)]  
  
##  <a name="setpressedimagelist"></a>CToolBarCtrl::SetPressedImageList  
 Задает список изображений, текущего элемента управления панель инструментов используется для представления кнопки в нажатом состоянии.  
  
```  
CImagelist* SetPressedImageList(
    int iImageID,   
    CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iImageID`|Отсчитываемый от нуля индекс списка изображений. Установите этот параметр равным нулю, если используется только один список изображений.|  
|[in] `pImageList`|Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий новый список изображений.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий предыдущего списка изображений для текущего элемента управления, или `NULL` Если такой список изображений не было задано.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_SETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787453) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает список изображений нажатой же список изображений по умолчанию.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_7.cpp)]  
  
##  <a name="setrows"></a>CToolBarCtrl::SetRows  
 Запрашивает у панели инструментов для изменения размера самого запрашиваемое количество строк.  
  
```  
void SetRows(
    int nRows,  
    BOOL bLarger,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `nRows`  
 Запрашиваемое количество строк.  
  
 `bLarger`  
 Указывает, следует использовать несколько строк или меньшее число строк, если запрашиваемое количество строк не может быть увеличена панели инструментов.  
  
 `lpRect`  
 Указывает на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, который получит ограничивающий прямоугольник на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Если панель инструментов не может изменяться в запрошенного числа или строки, будет изменяться либо следующий большего размера или следующего меньшего допустимый размер, в зависимости от значения `bLarger`. Если `bLarger` — **TRUE**, число новых строк будет больше запрошенного числа. Если `bLarger` — **FALSE**, число новых строк будет меньше запрошенного числа.  
  
 Если кнопки, которые могут быть упорядочены таким образом, что все строки имеют одинаковое число кнопок (за исключением возможно последней строки), заданное количество строк является действительным для панели инструментов. Например панель инструментов, которая содержит четыре кнопки может не соответствовать требованиям для три строки так, как бы быть короче последних двух строк. При попытке сделать его три строки, будет получена четыре строки при `bLarger` было **TRUE** и две строки, если `bLarger` было **FALSE**.  
  
 При наличии в качестве разделителей в панели инструментов, которые сложнее, правила когда заданное количество строк является действительным. Макет является вычисляемым, таким образом, что группы кнопки (кнопки с разделителем перед первым) и последней кнопки в группе никогда не подразделяются на несколько строк, если группа не может поместиться на одной строке.  
  
 Если группы не помещается на одной строке, следующей группы запустится в следующей строке, даже если он поместится в строке, где заканчивается большой группы. Это правило предназначено для сделать расстояние между наиболее заметно больших групп. Полученный вертикальной разделители, рассматриваются как строки.  
  
 Обратите внимание, что `SetRows` функция-член всегда будет выбран макет, который приведет наименьший размер панели инструментов. Создание панели инструментов с `TBSTYLE_WRAPABLE` стиль и затем размера элемента управления просто примените метода, описанного выше заданной ширины элемента управления.  
  
 Эта функция может вызываться только для панели инструментов, которые были созданы с помощью `TBSTYLE_WRAPABLE` стиля.  
  
##  <a name="setstate"></a>CToolBarCtrl::SetState  
 Задает состояние для указанной кнопки элемента управления toolbar.  
  
```  
BOOL SetState(
    int nID,  
    UINT nState);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки.  
  
 `nState`  
 Флаги состояния. Он может быть сочетанием значений, указанных для состояния кнопки в [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция особенно полезна, если нужно задать более одного из состояния кнопки. Чтобы просто установите для одного состояния, используйте один из следующих функций-членов: [EnableButton](#enablebutton), [CheckButton](#checkbutton), [HideButton](#hidebutton), [не определено](#indeterminate), или [PressButton](#pressbutton).  
  
##  <a name="setstyle"></a>CToolBarCtrl::SetStyle  
 Задает стили для элемента управления панели инструментов.  
  
```  
void SetStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Объект `DWORD` содержащий сочетание [стили элемента управления панель инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settooltips"></a>CToolBarCtrl::SetToolTips  
 Связывает всплывающая подсказка с элементом управления панели инструментов.  
  
```  
void SetToolTips(CToolTipCtrl* pTip);
```  
  
### <a name="parameters"></a>Параметры  
 *pTip*  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта.  
  
##  <a name="setwindowtheme"></a>CToolBarCtrl::SetWindowTheme  
 Задает стиль оформления `CToolBarCtrl` объекта.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержит визуальный стиль панели инструментов для установки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb787465) сообщения, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Пример MFC MFCIE](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CToolBar](../../mfc/reference/ctoolbar-class.md)

