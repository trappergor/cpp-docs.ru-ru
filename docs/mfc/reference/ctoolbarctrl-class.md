---
title: "CToolBarCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBarCtrl
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2d3ec23d6147299d9a615e9edb0d3f90680bbfac
ms.lasthandoff: 02/24/2017

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
|[CToolBarCtrl::AddBitmap](#addbitmap)|Добавляет один или несколько растровых изображений кнопки в список изображений кнопок, доступных для элемента управления панели инструментов.|  
|[CToolBarCtrl::AddButtons](#addbuttons)|Добавляет одну или несколько кнопок в элемент управления панели инструментов.|  
|[CToolBarCtrl::AddString](#addstring)|Добавляет новые строки, переданной в качестве идентификатора ресурса панели инструментов внутренний список строк.|  
|[CToolBarCtrl::AddStrings](#addstrings)|Добавляет новую строку или строки, передается как указатель на буфер строк, разделенных null, панели инструментов внутренний список строк.|  
|[CToolBarCtrl::AutoSize](#autosize)|Изменяет размер элемента управления панели инструментов.|  
|[CToolBarCtrl::ChangeBitmap](#changebitmap)|Изменение точечного рисунка для кнопки в текущий элемент управления панели инструментов.|  
|[CToolBarCtrl::CheckButton](#checkbutton)|Проверяет, или удаляет заданную кнопку в панели инструментов.|  
|[CToolBarCtrl::CommandToIndex](#commandtoindex)|Возвращает отсчитываемый от нуля индекс для кнопки, связанной с указанным идентификатором команды.|  
|[CToolBarCtrl::Create](#create)|Создает элемент управления панели инструментов и присоединяет его к `CToolBarCtrl` объекта.|  
|[CToolBarCtrl::CreateEx](#createex)|Создает элемент управления toolbar с указанным расширенные стили Windows и присоединяет его к `CToolBarCtrl` объекта.|  
|[CToolBarCtrl::Customize](#customize)|Отображает диалоговое окно Настройка панели инструментов.|  
|[CToolBarCtrl::DeleteButton](#deletebutton)|Удаление кнопки с панели инструментов.|  
|[CToolBarCtrl::EnableButton](#enablebutton)|Включает или отключает указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::GetAnchorHighlight](#getanchorhighlight)|Получает выделение привязки, Настройка панели инструментов.|  
|[CToolBarCtrl::GetBitmap](#getbitmap)|Извлекает индекс растровое изображение, связанное с кнопкой на панели инструментов.|  
|[CToolBarCtrl::GetBitmapFlags](#getbitmapflags)|Возвращает флаги, связанные с точечным рисунком панели инструментов.|  
|[CToolBarCtrl::GetButton](#getbutton)|Извлекает сведения о указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::GetButtonCount](#getbuttoncount)|Получает число кнопок панели инструментов.|  
|[CToolBarCtrl::GetButtonInfo](#getbuttoninfo)|Возвращает сведения о кнопке на панели инструментов.|  
|[CToolBarCtrl::GetButtonSize](#getbuttonsize)|Получает текущую ширину и высоту кнопок панели инструментов, в пикселях.|  
|[CToolBarCtrl::GetColorScheme](#getcolorscheme)|Возвращает цветовую схему текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::GetDisabledImageList](#getdisabledimagelist)|Получает список изображений, управления панели инструментов для отображения неактивных кнопок.|  
|[CToolBarCtrl::GetDropTarget](#getdroptarget)|Извлекает [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейс для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetHotImageList](#gethotimagelist)|Получает список изображений, управления панели инструментов используется для отображения кнопок «горячей». Кнопку в активном состоянии выделяется, когда указатель мыши находится над ним.|  
|[CToolBarCtrl::GetHotItem](#gethotitem)|Извлекает индекс модной на панели инструментов.|  
|[CToolBarCtrl::GetImageList](#getimagelist)|Получает список изображений, управления панели инструментов используется для отображения кнопки в состоянии по умолчанию.|  
|[CToolBarCtrl::GetInsertMark](#getinsertmark)|Получает текущий знак вставки для панели инструментов.|  
|[CToolBarCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Получает цвет, используемый для рисования знак вставки для панели инструментов.|  
|[CToolBarCtrl::GetItemRect](#getitemrect)|Возвращает прямоугольник, ограничивающий кнопки в панели инструментов.|  
|[CToolBarCtrl::GetMaxSize](#getmaxsize)|Возвращает общий размер всех видимой кнопки и разделители в панели инструментов.|  
|[CToolBarCtrl::GetMaxTextRows](#getmaxtextrows)|Получает максимальное количество строк текста, отображаемый на кнопке панели инструментов.|  
|[CToolBarCtrl::GetMetrics](#getmetrics)|Получает метрики элемента управления панели инструментов.|  
|[CToolBarCtrl::GetPadding](#getpadding)|Возвращает горизонтальное и вертикальное заполнения текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::GetPressedImageList](#getpressedimagelist)|Получает список изображений, текущий элемент управления панели инструментов используется для представления кнопки в нажатом состоянии.|  
|[CToolBarCtrl::GetRect](#getrect)|Возвращает ограничивающий прямоугольник для указанной кнопки.|  
|[CToolBarCtrl::GetRows](#getrows)|Получает число строк, кнопок, отображаемых на панели инструментов.|  
|[CToolBarCtrl::GetState](#getstate)|Получает сведения о состоянии от указанной кнопки в элементе управления панели инструментов, например ли он включен, нажата или проверки.|  
|[CToolBarCtrl::GetString](#getstring)|Извлекает строку, панели инструментов.|  
|[CToolBarCtrl::GetStyle](#getstyle)|Получает стили в настоящее время для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetToolTips](#gettooltips)|Получает дескриптор элемента управления всплывающей подсказки, если имеется, сопоставленный с элементом управления панели инструментов.|  
|[CToolBarCtrl::HideButton](#hidebutton)|Скрытие или отображение указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::HitTest](#hittest)|Определяет, где находится точка в элементе управления панели инструментов.|  
|[CToolBarCtrl::Indeterminate](#indeterminate)|Устанавливает или снимает неопределенном состоянии (серым) от указанной кнопки в панели инструментов.|  
|[CToolBarCtrl::InsertButton](#insertbutton)|Вставляет кнопку в панели инструментов.|  
|[CToolBarCtrl::InsertMarkHitTest](#insertmarkhittest)|Извлекает сведения о знак вставки для точки в панели инструментов.|  
|[CToolBarCtrl::IsButtonChecked](#isbuttonchecked)|Указывает, установлен ли флажок указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::IsButtonEnabled](#isbuttonenabled)|Указывает, включена ли кнопка, указанного в элементе управления панели инструментов.|  
|[CToolBarCtrl::IsButtonHidden](#isbuttonhidden)|Указывает, скрыт ли указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::IsButtonHighlighted](#isbuttonhighlighted)|Проверяет состояние выделения кнопки панели инструментов.|  
|[CToolBarCtrl::IsButtonIndeterminate](#isbuttonindeterminate)|Сообщает, является ли состояние указанной кнопки элемента управления toolbar неопределенное (серый).|  
|[CToolBarCtrl::IsButtonPressed](#isbuttonpressed)|Указывает, нажата ли указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::LoadImages](#loadimages)|Загружает растровых изображений в список изображений элемента управления панели инструментов.|  
|[CToolBarCtrl::MapAccelerator](#mapaccelerator)|Сопоставляет символ сочетаний клавиш для кнопки панели инструментов.|  
|[CToolBarCtrl::MarkButton](#markbutton)|Задает состояние выделения данной кнопки элемента управления toolbar.|  
|[CToolBarCtrl::MoveButton](#movebutton)|Перемещение кнопки из одного индекса на другой.|  
|[CToolBarCtrl::PressButton](#pressbutton)|Нажимает или отпускает указанную кнопку в панели инструментов.|  
|[CToolBarCtrl::ReplaceBitmap](#replacebitmap)|Заменяет точечного существующего точечного рисунка в текущий элемент управления панели инструментов.|  
|[CToolBarCtrl::RestoreState](#restorestate)|Восстанавливает состояние панели инструментов.|  
|[CToolBarCtrl::SaveState](#savestate)|Сохраняет состояние элемента панели инструментов.|  
|[CToolBarCtrl::SetAnchorHighlight](#setanchorhighlight)|Задает привязки выделения, Настройка панели инструментов.|  
|[CToolBarCtrl::SetBitmapSize](#setbitmapsize)|Задает размер точечных рисунков для добавления элемента управления панели инструментов.|  
|[CToolBarCtrl::SetButtonInfo](#setbuttoninfo)|Задает сведения для существующей кнопки в панели инструментов.|  
|[CToolBarCtrl::SetButtonSize](#setbuttonsize)|Задает размер кнопки для добавления элемента управления панели инструментов.|  
|[CToolBarCtrl::SetButtonStructSize](#setbuttonstructsize)|Указывает размер `TBBUTTON` структуры.|  
|[CToolBarCtrl::SetButtonWidth](#setbuttonwidth)|Задает кнопку минимальное и максимальное значения ширины в панели инструментов.|  
|[CToolBarCtrl::SetCmdID](#setcmdid)|Задает отправку окна-владельца при нажатии кнопки указанный идентификатор команды.|  
|[CToolBarCtrl::SetColorScheme](#setcolorscheme)|Задает цвет элемента панели инструментов.|  
|[CToolBarCtrl::SetDisabledImageList](#setdisabledimagelist)|Задает список изображений, который будет использоваться элементом управления панели инструментов для отображения неактивных кнопок.|  
|[CToolBarCtrl::SetDrawTextFlags](#setdrawtextflags)|Задает флаги в функцию Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), который используется для отрисовки текста в указываемом прямоугольнике, отформатированное в соответствии со установке флагов.|  
|[CToolBarCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::SetHotImageList](#sethotimagelist)|Задает список изображений, используемый элементом управления панели инструментов для отображения кнопок «горячей».|  
|[CToolBarCtrl::SetHotItem](#sethotitem)|Задает горячей элемента панели инструментов.|  
|[CToolBarCtrl::SetImageList](#setimagelist)|Задает список изображений, панели инструментов будет использовать для отображения кнопок, которые находятся в состоянии по умолчанию.|  
|[CToolBarCtrl::SetIndent](#setindent)|Задает отступ для первой кнопки элемента управления toolbar.|  
|[CToolBarCtrl::SetInsertMark](#setinsertmark)|Задает текущий знак вставки для панели инструментов.|  
|[CToolBarCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Задает цвет, используемый для рисования знак вставки для панели инструментов.|  
|[CToolBarCtrl::SetMaxTextRows](#setmaxtextrows)|Задает максимальное количество строк текста, отображаемый на кнопке панели инструментов.|  
|[CToolBarCtrl::SetMetrics](#setmetrics)|Задает метрики элемента управления панели инструментов.|  
|[CToolBarCtrl::SetOwner](#setowner)|Задает окно, чтобы получать сообщения уведомления из панели инструментов.|  
|[CToolBarCtrl::SetPadding](#setpadding)|Задает горизонтальное и вертикальное заполнение текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::SetPressedImageList](#setpressedimagelist)|Задает список изображений, текущий элемент управления панели инструментов используется для представления кнопки в нажатом состоянии.|  
|[CToolBarCtrl::SetRows](#setrows)|Задает количество строк, кнопок, отображаемых на панели инструментов.|  
|[CToolBarCtrl::SetState](#setstate)|Задает состояние для указанной кнопки в панели инструментов.|  
|[CToolBarCtrl::SetStyle](#setstyle)|Задает стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::SetToolTips](#settooltips)|Связывает управления всплывающей подсказки с панели инструментов.|  
|[CToolBarCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль элемента управления панели инструментов.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент управления (и, следовательно, `CToolBarCtrl` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Панель инструментов общих элементов управления Windows является прямоугольной дочернего окна, содержащий одну или несколько кнопок. Эти кнопки можно отобразить растрового изображения и строки. Когда пользователь нажимает кнопку, он отправляет сообщение команды панели инструментов окна-владельца. Как правило кнопок в панели инструментов соответствуют элементам в меню приложения; они предоставляют более прямолинейным способом для пользователя для доступа к командам приложения.  
  
 `CToolBarCtrl`объекты содержат несколько важных внутренних структур данных: список точечного рисунка для изображения кнопки или списка изображений, список строк метки кнопки и список `TBBUTTON` структурам связать изображение или строка с позиции, стиль, состояние и идентификатор кнопки команд. Каждый из элементов этих структур данных ссылается отсчитываемый от нуля индекс. Прежде чем использовать `CToolBarCtrl` объекта, необходимо настроить эти структуры данных. Список строк может использоваться только для метки кнопок; не удается извлечь строки из панели инструментов.  
  
 Для использования `CToolBarCtrl` объекта, обычно выполняются следующие действия:  
  
1.  Создать `CToolBarCtrl` объекта.  
  
2.  Вызов [создать](#create) для создания стандартного элемента управления панели инструментов Windows и присоединить его к `CToolBarCtrl` объекта. Указывает стиль панели инструментов с помощью стилей, таких как **TBSTYLE_TRANSPARENT** прозрачные панели инструментов или **TBSTYLE_DROPDOWN** для панели инструментов, которая поддерживает кнопки раскрывающегося списка.  
  
3.  Определите способ кнопки на панели инструментов отображается:  
  
    -   Использование точечных рисунков кнопкам, добавить точечного рисунка для кнопки панели инструментов с помощью [AddBitmap](#addbitmap).  
  
    -   Чтобы использовать изображения, отображаемые в списке изображений для кнопки, укажите список изображений, вызвав [SetImageList](#setimagelist), [SetHotImageList](#sethotimagelist), или [SetDisabledImageList](#setdisabledimagelist).  
  
    -   Чтобы использовать строку метки для кнопок, добавлять строки панели инструментов, вызвав [AddString](#addstring) или [AddStrings](#addstrings).  
  
4.  Добавить на панель инструментов кнопку структуры путем вызова [AddButtons](#addbuttons).  
  
5.  Если всплывающие подсказки для кнопки панели инструментов в окне владельца, не `CFrameWnd`, вам нужно обрабатывать **TTN_NEEDTEXT** сообщений в панели инструментов окна-владельца, как описано в [обработка уведомлений совет средство](../../mfc/handling-tool-tip-notifications.md). Если родительское окно инструментов является производным от `CFrameWnd`, всплывающие подсказки отображаются без дополнительных усилий со стороны пользователя, так как `CFrameWnd` предоставляет обработчик по умолчанию.  
  
6.  Если требуется, чтобы пользователь имел возможность настраивать панели инструментов, обработку сообщений уведомления настройки в окна-владельца, как описано в [обработка уведомлений о настройке](../../mfc/handling-customization-notifications.md).  
  
 Можно использовать [SaveState](#savestate) сохранить текущее состояние элемента управления панели инструментов в реестре и [RestoreState](#restorestate) для восстановления состояния на основе информации, ранее хранившиеся в реестре. Помимо сохранения состояния панели инструментов между использует приложения, приложения обычно хранят состояние, прежде чем пользователь начинает Настройка панели инструментов в случае, если пользователь хочет позже восстановить исходное состояние панели инструментов.  
  
## <a name="support-for-internet-explorer-version-40-and-later"></a>Поддержка Internet Explorer версии 4.0 и более поздних версий  
 Для поддержки функциональных возможностей, описанное в Internet Explorer 4.0 и более поздних версиях MFC предоставляет поддержки списка изображений и прозрачной и плоский стили для элементов управления панели инструментов.  
  
 Прозрачные панели инструментов позволяет клиенту под панелью инструментов видны сквозь. Создание прозрачного инструментов, использовать оба **TBSTYLE_FLAT** и **TBSTYLE_TRANSPARENT** стили. Прозрачные панели инструментов компонентов отслеживание; то есть при перемещении указателя мыши на кнопку в активном состоянии на панели инструментов, изменяется внешний вид кнопки. Панели инструментов, созданные с помощью только **TBSTYLE_FLAT** стиль будет содержать кнопки, которые не являются прозрачными.  
  
 Поддержка списков изображений позволяет гибкость управления, поведение по умолчанию, наиболее часто используемыми изображениями и отключенные изображения. Используйте [GetImageList](#getimagelist), [GetHotImageList](#gethotimagelist), и [GetDisabledImageList](#getdisabledimagelist) с прозрачным инструментов для управления изображения в соответствии с его состояние:  
  
 Дополнительные сведения об использовании `CToolBarCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CToolBarCtrl с помощью](../../mfc/using-ctoolbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-nameaddbitmapa--ctoolbarctrladdbitmap"></a><a name="addbitmap"></a>CToolBarCtrl::AddBitmap  
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
 Количество изображений кнопки в растровом изображении.  
  
 `nBitmapID`  
 Идентификатор ресурса растрового изображения, содержащий изображение кнопки или изображения.  
  
 `pBitmap`  
 Указатель на `CBitmap` объект, содержащий изображение кнопки или изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого нового изображения в случае успешного выполнения; в противном случае — значение 1.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать интерфейс Windows API [CreateMappedBitmap](http://msdn.microsoft.com/library/windows/desktop/bb787467) для сопоставления цветов перед добавлением растровое изображение в панели инструментов. Если передать указатель на **CBitMap** объекта, необходимо убедиться, что точечный рисунок не удаляются до, после удаления панели инструментов.  
  
##  <a name="a-nameaddbuttonsa--ctoolbarctrladdbuttons"></a><a name="addbuttons"></a>CToolBarCtrl::AddButtons  
 Добавляет одну или несколько кнопок в элемент управления панели инструментов.  
  
```  
BOOL AddButtons(
    int nNumButtons,  
    LPTBBUTTON lpButtons);
```  
  
### <a name="parameters"></a>Параметры  
 `nNumButtons`  
 Количество добавляемых кнопок.  
  
 `lpButtons`  
 Адрес массива `TBBUTTON` структур, содержащих сведения о добавляемых кнопках. Должно быть одинаковое количество элементов в массиве, как кнопки, определяемое `nNumButtons`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 `lpButtons` Указывает ли указатель на массив `TBBUTTON` структуры. Каждый `TBBUTTON` структуры связывают кнопки, добавляемый с стиль кнопки, состояние образа или строку, идентификатор команды и определенные пользователем данные:  
  
 `typedef struct _TBBUTTON {`  
  
 `int iBitmap;// zero-based index of button image`  
  
 `int idCommand;  // command to be sent when button pressed`  
  
 `BYTE fsState;   // button state--see below`  
  
 `BYTE fsStyle;   // button style--see below`  
  
 `DWORD dwData;   // application-defined value`  
  
 `int iString;// zero-based index of button label string`  
  
 `} TBBUTTON;`  
  
 Ниже приведены элементы.  
  
 **iBitmap**  
 Отсчитываемый от нуля индекс изображение кнопки, -1, если нет изображения для этой кнопки.  
  
 **idCommand**  
 Идентификатор команды, связанный с кнопки. Этот идентификатор отправляется **WM_COMMAND** сообщения при нажатии кнопки. Если **fsStyle** член имеет `TBSTYLE_SEP` значение этого элемента должно быть равно нулю.  
  
 **fsState**  
 Флаги состояния кнопок. Это может быть сочетанием значений, перечисленных ниже:  
  
- `TBSTATE_CHECKED`Кнопка имеет **TBSTYLE_CHECKED** стиля и нажат.  
  
- `TBSTATE_ENABLED`Кнопки, принимающее вводимые пользователем данные. Кнопка, которая не имеет это состояние не принимает входные данные пользователя и отображается серым цветом.  
  
- `TBSTATE_HIDDEN`Кнопка не отображается и не может реагировать на действия пользователя.  
  
- `TBSTATE_INDETERMINATE`Кнопка отображается серым цветом.  
  
- `TBSTATE_PRESSED`Кнопка нажата.  
  
- `TBSTATE_WRAP`Кнопки ставится разрыв строки. Необходимо также иметь кнопки `TBSTATE_ENABLED` состояния.  
  
 **fsStyle**  
 Стиль кнопки. Это может быть сочетанием значений, перечисленных ниже:  
  
- `TBSTYLE_BUTTON`Создает стандартные кнопки.  
  
- `TBSTYLE_CHECK`Создает кнопку, которая переключает между состояниями нажатого и ненажатое при каждом щелчке по нему. Кнопка имеет другой цвет фона, когда он находится в нажатом состоянии.  
  
- `TBSTYLE_CHECKGROUP`Создает кнопку с галочкой, остается в нажатом положении, пока не будет нажата другая кнопка в группе.  
  
- `TBSTYLE_GROUP`Создает кнопку, которая остается в нажатом положении, пока не будет нажата другая кнопка в группе.  
  
- `TBSTYLE_SEP`Создает разделитель, предоставляя небольшой разрыв между группы кнопок. Кнопка с этим стилем не реагировать на действия пользователя.  
  
 `dwData`  
 Определенные пользователем данные.  
  
 **iString**  
 Отсчитываемый от нуля индекс строки для использования в качестве кнопки метки, -1, если строка не для этой кнопки.  
  
 Список с изображения или строки, индекс которого можно предоставить необходимо ранее были добавлены в элемент управления toolbar с помощью [AddBitmap](#addbitmap), [AddString](#addstring), или [AddStrings](#addstrings).  
  
##  <a name="a-nameaddstringa--ctoolbarctrladdstring"></a><a name="addstring"></a>CToolBarCtrl::AddString  
 Добавляет новые строки, переданной в качестве идентификатора ресурса панели инструментов внутренний список строк.  
  
```  
int AddString(UINT nStringID);
```  
  
### <a name="parameters"></a>Параметры  
 *nStringID*  
 Идентификатор ресурса строкового ресурса, чтобы добавить список строк панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого новые строки, добавленной в случае успешного выполнения; в противном случае — значение -1.  
  
##  <a name="a-nameaddstringsa--ctoolbarctrladdstrings"></a><a name="addstrings"></a>CToolBarCtrl::AddStrings  
 Добавляет новую строку или строки в список строк, доступных для элемента управления панели инструментов.  
  
```  
int AddStrings(LPCTSTR lpszStrings);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszStrings*  
 Адрес буфера, который содержит одну или несколько строк нулем, чтобы добавить список строк панели инструментов. Последняя строка должна заканчиваться точкой с двумя символами null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого новые строки, добавленной в случае успешного выполнения; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Символ null должны быть разделены строк в буфере. Необходимо убедиться, что последняя строка имеет два конца. Чтобы правильно отформатировать строковую константу, можно написать его как:  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#72;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_1.cpp)]  
  
 или  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#73;](../../mfc/codesnippet/cpp/ctoolbarctrl-class_2.cpp)]  
  
 Не следует передавать `CString` объекта для этой функции, поскольку он не может быть более одного символа null `CString`.  
  
##  <a name="a-nameautosizea--ctoolbarctrlautosize"></a><a name="autosize"></a>CToolBarCtrl::AutoSize  
 Изменяет элемент управления в панель инструментов полностью.  
  
```  
void AutoSize();
```  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует вызывать при изменении размера родительского окна или при изменении размера панели инструментов (например, при установке размера кнопки или растрового изображения или добавить строки).  
  
##  <a name="a-namechangebitmapa--ctoolbarctrlchangebitmap"></a><a name="changebitmap"></a>CToolBarCtrl::ChangeBitmap  
 Изменение точечного рисунка для кнопки в текущий элемент управления панели инструментов.  
  
```  
BOOL ChangeBitmap(
    int idButton,   
    int iBitmap);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `idButton`|Команда идентификатор кнопки, которая будет получать новое растровое изображение.|  
|[in] `iBitmap`|Отсчитываемый от нуля индекс изображения в списке изображений текущего элемента управления панели инструментов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод выполнен успешно, система отображает указанное изображение в указанную кнопку.  
  
 Этот метод отправляет [TB_CHANGEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787301) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода изменяется растровое изображение для **сохранения файла** кнопку растровое изображение для **о** кнопки.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_3.cpp)]  
  
##  <a name="a-namecheckbuttona--ctoolbarctrlcheckbutton"></a><a name="checkbutton"></a>CToolBarCtrl::CheckButton  
 Проверяет, или удаляет заданную кнопку в панели инструментов.  
  
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
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Когда переключатель кажется нажатия. Если вы хотите изменить более одного состояния кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо.  
  
##  <a name="a-namecommandtoindexa--ctoolbarctrlcommandtoindex"></a><a name="commandtoindex"></a>CToolBarCtrl::CommandToIndex  
 Возвращает отсчитываемый от нуля индекс для кнопки, связанной с указанным идентификатором команды.  
  
```  
UINT CommandToIndex(UINT nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды, кнопка индекса вы хотите найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс для кнопки, связанной с идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecreatea--ctoolbarctrlcreate"></a><a name="create"></a>CToolBarCtrl::Create  
 Создает элемент управления панели инструментов и присоединяет его к `CToolBarCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления панели инструментов. Панели инструментов всегда должен иметь **WS_CHILD** стиль. Кроме того, можно указать любое сочетание стили окна и панели инструментов, как описано в разделе **примечания**.  
  
 `rect`  
 При необходимости указывает размер и положение элемента управления панели инструментов. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает элемент управления toolbar родительского окна. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Создании `CToolBarCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает элемент управления панели инструментов и присоединяет его к `CToolBarCtrl` объекта. Применяются следующие стили окна для элемента управления панели инструментов.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
 В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] описание стили окна.  
  
 Дополнительно можно применить сочетание [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Применить сочетание стили панели инструментов на элемент управления или кнопки сами. Стили, описаны в разделе [панели инструментов и стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb760439) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Чтобы использовать панель инструментов расширенные стили, вызвать [SetExtendedStyle](#setextendedstyle) после вызова **создать**. Чтобы создать панель инструментов с расширенные стили окна, вызовите [CToolBarCtrl::CreateEx](#createex) вместо **создать**.  
  
 Панели инструментов автоматически задает размер и положение окна инструментов. Высота основана на высоте кнопок на панели инструментов. Ширина является таким же, как Ширина клиентской области родительского окна. `CCS_TOP` И `CCS_BOTTOM` стили определяют, расположено ли вдоль верхней или нижней части клиентской области панели инструментов. По умолчанию панель инструментов имеет `CCS_TOP` стиль.  
  
##  <a name="a-namecreateexa--ctoolbarctrlcreateex"></a><a name="createex"></a>CToolBarCtrl::CreateEx  
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
 Задает стиль элемента управления панели инструментов. Панели инструментов всегда должен иметь **WS_CHILD** стиль. Кроме того, можно указать любое сочетание стили окна и панели инструментов, как описано в **примечания** раздел [создать](#create).  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**. **CreateEx** создает элемент управления с помощью расширенных стилей Windows, заданные `dwExStyle`. Расширенные стили, определенные для элемента управления с помощью набора [SetExtendedStyle](#setextendedstyle). Например, используйте `CreateEx` установка стилей, таких как **WS_EX_CONTEXTHELP**, но использовать `SetExtendedStyle` установка стилей, таких как **TBSTYLE_EX_DRAWDDARROWS**. Дополнительные сведения см. в разделе стили, описанные в [расширенные стили панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760430) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namectoolbarctrla--ctoolbarctrlctoolbarctrl"></a><a name="ctoolbarctrl"></a>CToolBarCtrl::CToolBarCtrl  
 Создает объект `CToolBarCtrl`.  
  
```  
CToolBarCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [создать](#create) необходимо разрешить использование панели инструментов.  
  
##  <a name="a-namecustomizea--ctoolbarctrlcustomize"></a><a name="customize"></a>CToolBarCtrl::Customize  
 Отображает диалоговое окно Настройка панели инструментов.  
  
```  
void Customize();
```  
  
### <a name="remarks"></a>Примечания  
 Это диалоговое окно предназначено позволяет пользователю настроить, добавляя и удаляя кнопки панели инструментов. Для поддержки настройки, панель инструментов родительского окна необходимо обрабатывать сообщения уведомления настройки, как описано в [обработка уведомлений о настройке](../../mfc/handling-customization-notifications.md). Панель инструментов также должен создан с `CCS_ADJUSTABLE` стиля, как описано в [CToolBarCtrl::Create](#create).  
  
 Дополнительные сведения см. в статье базы знаний Q241850: PRB: вызов CToolBarCtrl::Customize не остается видимым настройки диалогового окна.  
  
##  <a name="a-namedeletebuttona--ctoolbarctrldeletebutton"></a><a name="deletebutton"></a>CToolBarCtrl::DeleteButton  
 Удаление кнопки с панели инструментов.  
  
```  
BOOL DeleteButton(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопку для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenablebuttona--ctoolbarctrlenablebutton"></a><a name="enablebutton"></a>CToolBarCtrl::EnableButton  
 Включает или отключает указанную кнопку в панели инструментов.  
  
```  
BOOL EnableButton(
    int nID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, чтобы включить или отключить.  
  
 `bEnable`  
 **Значение TRUE,** для включения кнопки. **FALSE** для выключения кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 При включении кнопки можно нажата и проверки. Если вы хотите изменить более одного состояния кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо.  
  
##  <a name="a-namegetanchorhighlighta--ctoolbarctrlgetanchorhighlight"></a><a name="getanchorhighlight"></a>CToolBarCtrl::GetAnchorHighlight  
 Получает выделение привязки, Настройка панели инструментов.  
  
```  
BOOL GetAnchorHighlight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, выделение привязка включена. Если значение равно нулю, выделение привязки будет отключена.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787313), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbitmapa--ctoolbarctrlgetbitmap"></a><a name="getbitmap"></a>CToolBarCtrl::GetBitmap  
 Извлекает индекс растровое изображение, связанное с кнопкой на панели инструментов.  
  
```  
int GetBitmap(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, индекс которого точечный рисунок которой требуется извлечь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс точечного рисунка, если успешно, или нуль, в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Реализует функции [TB_GETBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787315) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbitmapflagsa--ctoolbarctrlgetbitmapflags"></a><a name="getbitmapflags"></a>CToolBarCtrl::GetBitmapFlags  
 Получает флаги точечный рисунок из панели инструментов.  
  
```  
UINT GetBitmapFlags() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** с **TBBF_LARGE** установлен флаг, если отображение поддерживает растровые изображения панели инструментов, в противном случае снимите флажок.  
  
### <a name="remarks"></a>Примечания  
 Его следует вызывать после создания панели инструментов, но перед добавлением растровые изображения панели инструментов. Возвращаемое значение указывает, поддерживает ли отображение большие точечные рисунки. Если отображение поддерживает большие точечные рисунки и выберите их, вызовите [SetBitmapSize](#setbitmapsize) и [SetButtonSize](#setbuttonsize) перед добавлением большую битовую карту с помощью [AddBitmap](#addbitmap).  
  
##  <a name="a-namegetbuttona--ctoolbarctrlgetbutton"></a><a name="getbutton"></a>CToolBarCtrl::GetButton  
 Извлекает сведения о указанную кнопку в панели инструментов.  
  
```  
BOOL GetButton(
    int nIndex,  
    LPTBBUTTON lpButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки, для которого необходимо получить сведения.  
  
 `lpButton`  
 Адрес `TBBUTTON` структуру, для получения копии кнопку сведения. В разделе [CToolBarCtrl::AddButtons](#addbuttons) сведения о `TBBUTTON` структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namegetbuttoncounta--ctoolbarctrlgetbuttoncount"></a><a name="getbuttoncount"></a>CToolBarCtrl::GetButtonCount  
 Получает число кнопок панели инструментов.  
  
```  
int GetButtonCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число кнопок.  
  
##  <a name="a-namegetbuttoninfoa--ctoolbarctrlgetbuttoninfo"></a><a name="getbuttoninfo"></a>CToolBarCtrl::GetButtonInfo  
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
 Указатель на [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) структуру, которая получает данные о кнопке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс кнопки в случае успешного выполнения; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787321), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbuttonsizea--ctoolbarctrlgetbuttonsize"></a><a name="getbuttonsize"></a>CToolBarCtrl::GetButtonSize  
 Возвращает размер кнопки панели инструментов.  
  
```  
DWORD GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `DWORD` значение, которое содержит значения ширины и высоты в LOWORD и HIWORD, соответственно.  
  
##  <a name="a-namegetbuttontexta--ctoolbarctrlgetbuttontext"></a><a name="getbuttontext"></a>CToolBarCtrl::GetButtonText  
 Получает отображаемый текст указанную кнопку на текущий элемент управления панели инструментов.  
  
```  
CString GetButtonText(int idButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `idButton`|Идентификатор для кнопки извлекается которого отображаемого текста.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/using-cstring.md) , содержащий отображаемый текст указанную кнопку.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETBUTTONTEXT](http://msdn.microsoft.com/library/windows/desktop/bb787325) сообщения, которое описано в пакете Windows SDK.  
  
##  <a name="a-namegetcolorschemea--ctoolbarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>CToolBarCtrl::GetColorScheme  
 Возвращает цветовую схему текущего элемента управления панели инструментов.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpColorScheme) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpColorScheme`|Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структуру, которая получает сведения о схеме цвета. При возвращении данного метода, структура описывает цвет выделения и цвет тени панели инструментов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787327) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdisabledimagelista--ctoolbarctrlgetdisabledimagelist"></a><a name="getdisabledimagelist"></a>CToolBarCtrl::GetDisabledImageList  
 Получает список изображений, управления панели инструментов для отображения неактивных кнопок.  
  
```  
CImageList* GetDisabledImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, или **NULL** Если список отключенных изображений не установлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787329), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Реализация MFC `GetDisabledImageList` использует `CImageList` изображения объекта, содержащего кнопки панели инструментов вместо дескриптор списка изображений.  
  
##  <a name="a-namegetdroptargeta--ctoolbarctrlgetdroptarget"></a><a name="getdroptarget"></a>CToolBarCtrl::GetDropTarget  
 Извлекает [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейс для элемента управления панели инструментов.  
  
```  
HRESULT GetDropTarget(IDropTarget** ppDropTarget) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppDropTarget`  
 Указатель на [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) указатель на интерфейс. Если возникает ошибка, **NULL** указатель помещается в этот адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `HRESULT` значение указывает на успешное или неуспешное выполнение операции.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787343), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetextendedstylea--ctoolbarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CToolBarCtrl::GetExtendedStyle  
 Извлекает расширенные стили для элемента управления панели инструментов.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` , представляющий расширенные стили в настоящее время для панели инструментов. Список стилей см. в разделе [расширенные стили панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760430)в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787331), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegethotimagelista--ctoolbarctrlgethotimagelist"></a><a name="gethotimagelist"></a>CToolBarCtrl::GetHotImageList  
 Получает список изображений, управления панели инструментов используется для отображения кнопок «горячей». Кнопку в активном состоянии выделяется, когда указатель мыши находится над ним.  
  
```  
CImageList* GetHotImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, или **NULL** Если список отключенных изображений не установлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787334), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Кнопку в активном состоянии выделяется, когда указатель мыши находится над ним.  
  
##  <a name="a-namegethotitema--ctoolbarctrlgethotitem"></a><a name="gethotitem"></a>CToolBarCtrl::GetHotItem  
 Извлекает индекс модной на панели инструментов.  
  
```  
int GetHotItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс модной на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787336), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--ctoolbarctrlgetimagelist"></a><a name="getimagelist"></a>CToolBarCtrl::GetImageList  
 Получает список изображений, управления панели инструментов используется для отображения кнопки в состоянии по умолчанию.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, или **NULL** Если список изображений не установлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787337), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetinsertmarka--ctoolbarctrlgetinsertmark"></a><a name="getinsertmark"></a>CToolBarCtrl::GetInsertMark  
 Получает текущий знак вставки для панели инструментов.  
  
```  
void GetInsertMark(TBINSERTMARK* ptbim) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ptbim`  
 Указатель на [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) структуру, которая получает знак вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787338), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetinsertmarkcolora--ctoolbarctrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CToolBarCtrl::GetInsertMarkColor  
 Получает цвет, используемый для рисования знак вставки для панели инструментов.  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее текущий цвет метки вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787339), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetitemrecta--ctoolbarctrlgetitemrect"></a><a name="getitemrect"></a>CToolBarCtrl::GetItemRect  
 Возвращает прямоугольник, ограничивающий кнопки в панели инструментов.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс кнопки, для которого необходимо получить сведения.  
  
 `lpRect`  
 Адрес [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта, получающая координаты ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не извлекает ограничивающий прямоугольник для кнопки, состояние которого имеет значение `TBSTATE_HIDDEN`.  
  
##  <a name="a-namegetmaxsizea--ctoolbarctrlgetmaxsize"></a><a name="getmaxsize"></a>CToolBarCtrl::GetMaxSize  
 Возвращает общий размер всех видимой кнопки и разделители в панели инструментов.  
  
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
  
##  <a name="a-namegetmaxtextrowsa--ctoolbarctrlgetmaxtextrows"></a><a name="getmaxtextrows"></a>CToolBarCtrl::GetMaxTextRows  
 Получает максимальное количество строк текста, отображаемый на кнопке панели инструментов.  
  
```  
int GetMaxTextRows() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное количество строк текста, отображаемый на кнопке панели инструментов.  
  
##  <a name="a-namegetmetricsa--ctoolbarctrlgetmetrics"></a><a name="getmetrics"></a>CToolBarCtrl::GetMetrics  
 Получает метрики из `CToolBarCtrl` объекта.  
  
```  
void GetMetrics(LPTBMETRICS ptbm) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ptbm`  
 Указатель на [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) структуры `CToolBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TB_GETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787342) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpaddinga--ctoolbarctrlgetpadding"></a><a name="getpadding"></a>CToolBarCtrl::GetPadding  
 Возвращает горизонтальное и вертикальное заполнения текущего элемента управления панели инструментов.  
  
```  
BOOL GetPadding(
    int* pnHorzPadding,   
    int* pnVertPadding) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pnHorzPadding`|Целое число, Получает горизонтальный отступ элемента управления панели инструментов, в пикселях.|  
|[выходной] `pnVertPadding`|Целое число, Получает вертикальный отступ элемента управления панели инструментов, в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787344) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpressedimagelista--ctoolbarctrlgetpressedimagelist"></a><a name="getpressedimagelist"></a>CToolBarCtrl::GetPressedImageList  
 Получает список изображений, текущий элемент управления панели инструментов используется для представления кнопки в нажатом состоянии.  
  
```  
CImageList* GetPressedImageList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий список изображений для текущего элемента управления или `NULL` Если такой список изображений не установлен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_GETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787345) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrecta--ctoolbarctrlgetrect"></a><a name="getrect"></a>CToolBarCtrl::GetRect  
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
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры для получения информации о ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** при успехе; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb787346), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrowsa--ctoolbarctrlgetrows"></a><a name="getrows"></a>CToolBarCtrl::GetRows  
 Получает число строк, кнопок, отображаемых элементом управления панели инструментов.  
  
```  
int GetRows() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк, кнопок, отображаемых на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что количество строк всегда один, если не был создан панели инструментов `TBSTYLE_WRAPABLE` стиль.  
  
##  <a name="a-namegetstatea--ctoolbarctrlgetstate"></a><a name="getstate"></a>CToolBarCtrl::GetState  
 Получает сведения о состоянии от указанной кнопки в элементе управления панели инструментов, например ли он включен, нажата или проверки.  
  
```  
int GetState(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, для которого необходимо получить сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сведения о состоянии кнопки в случае успешного выполнения или – 1 в противном случае. Сведения о состоянии кнопка может быть сочетанием значений, перечисленных в [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="remarks"></a>Примечания  
 Эта функция особенно полезна, если вы хотите получить несколько состояний кнопки. Чтобы просто получить одно состояние, используйте один из следующих функций-членов: [IsButtonEnabled](#isbuttonenabled), [IsButtonChecked](#isbuttonchecked), [IsButtonPressed](#isbuttonpressed), [IsButtonHidden](#isbuttonhidden), или [IsButtonIndeterminate](#isbuttonindeterminate). Тем не менее `GetState` функция-член является единственным способом обнаружения `TBSTATE_WRAP` кнопку состояние.  
  
##  <a name="a-namegetstringa--ctoolbarctrlgetstring"></a><a name="getstring"></a>CToolBarCtrl::GetString  
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
 Указатель на буфер, который используется для возврата строки.  
  
 *cchMaxLen*  
 Длина буфера в байтах.  
  
 `str`  
 Строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки, в случае успеха, -1, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_GETSTRING](http://msdn.microsoft.com/library/windows/desktop/bb787349), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstylea--ctoolbarctrlgetstyle"></a><a name="getstyle"></a>CToolBarCtrl::GetStyle  
 Возвращает стили, примененные к элементу управления панели инструментов.  
  
```  
DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` содержащий сочетание [стили элемента управления панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettooltipsa--ctoolbarctrlgettooltips"></a><a name="gettooltips"></a>CToolBarCtrl::GetToolTips  
 Получает дескриптор элемента управления всплывающей подсказки, если имеется, сопоставленный с элементом управления панели инструментов.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, связанный с этой панели инструментов или **NULL** Если панели управления не связан всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Поскольку элемент управления toolbar обычно создает и обслуживает собственный управления всплывающей подсказки, большинство программ не требуется для вызова этой функции.  
  
##  <a name="a-namehittesta--ctoolbarctrlhittest"></a><a name="hittest"></a>CToolBarCtrl::HitTest  
 Определяет, где находится точка в элементе управления панели инструментов.  
  
```  
int HitTest(LPPOINT ppt) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppt`  
 Указатель на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, содержащую Координата по оси x для попадания в **x** член и Координата y в которой произведен щелчок тестирования в **y** член. Координаты указываются относительно клиентской области панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, указывающее расположение точки на панели инструментов. Если значение равно&0; или положительное значение, возвращаемое значение является отсчитываемый от нуля индекс элемента nonseparator, в которой находится точка.  
  
 Если возвращаемое значение является отрицательным, точка не находится внутри кнопки. Абсолютное значение возвращаемого значения — индекс элемента разделителя или ближайшего элемента nonseparator.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787360), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehidebuttona--ctoolbarctrlhidebutton"></a><a name="hidebutton"></a>CToolBarCtrl::HideButton  
 Скрытие или отображение указанную кнопку в панели инструментов.  
  
```  
BOOL HideButton(
    int nID,  
    BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, чтобы скрыть или отобразить.  
  
 `bHide`  
 **Значение TRUE,** для скрытия кнопки, **FALSE** , чтобы показать его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите изменить более одного состояния кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо.  
  
##  <a name="a-nameindeterminatea--ctoolbarctrlindeterminate"></a><a name="indeterminate"></a>CToolBarCtrl::Indeterminate  
 Устанавливает или снимает неопределенное состояние указанную кнопку в панели инструментов.  
  
```  
BOOL Indeterminate(
    int nID,  
    BOOL bIndeterminate = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки, неопределенное состояние которой нужно установить или очистить.  
  
 *bIndeterminate*  
 **Значение TRUE,** неопределенное состояние для указанной кнопки **FALSE** снимите его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Неопределенный кнопки отображаются серым цветом, такие, как будет выглядеть как кнопки «Полужирный» на панели инструментов текстового редактора при выделение текста содержит символы полужирным и обычным. Если вы хотите изменить более одного состояния кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо.  
  
##  <a name="a-nameinsertbuttona--ctoolbarctrlinsertbutton"></a><a name="insertbutton"></a>CToolBarCtrl::InsertButton  
 Вставляет кнопку в панели инструментов.  
  
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
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Список с изображения или строки, индекс которого можно предоставить необходимо ранее были добавлены в элемент управления toolbar с помощью [AddBitmap](#addbitmap), [AddString](#addstring), или [AddStrings](#addstrings).  
  
##  <a name="a-nameinsertmarkhittesta--ctoolbarctrlinsertmarkhittest"></a><a name="insertmarkhittest"></a>CToolBarCtrl::InsertMarkHitTest  
 Извлекает сведения о знак вставки для точки в панели инструментов.  
  
```  
BOOL InsertMarkHitTest(
    LPPOINT ppt,  
    LPTBINSERTMARK ptbim) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppt`  
 Указатель на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, содержащую попадания координаты относительно клиентской области панели инструментов.  
  
 `ptbim`  
 Указатель на [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) структуру, которая получает сведения о знак вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb787367), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisbuttoncheckeda--ctoolbarctrlisbuttonchecked"></a><a name="isbuttonchecked"></a>CToolBarCtrl::IsButtonChecked  
 Определяет, проверяется ли указанную кнопку в панели инструментов.  
  
```  
BOOL IsButtonChecked(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если она нажата; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить несколько состояний кнопки.  
  
##  <a name="a-nameisbuttonenableda--ctoolbarctrlisbuttonenabled"></a><a name="isbuttonenabled"></a>CToolBarCtrl::IsButtonEnabled  
 Определяет, включена ли кнопка, указанного в элементе управления панели инструментов.  
  
```  
BOOL IsButtonEnabled(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка включена; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить несколько состояний кнопки.  
  
##  <a name="a-nameisbuttonhiddena--ctoolbarctrlisbuttonhidden"></a><a name="isbuttonhidden"></a>CToolBarCtrl::IsButtonHidden  
 Определяет, является ли скрытым указанную кнопку в панели инструментов.  
  
```  
BOOL IsButtonHidden(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка скрыта; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить несколько состояний кнопки.  
  
##  <a name="a-nameisbuttonhighlighteda--ctoolbarctrlisbuttonhighlighted"></a><a name="isbuttonhighlighted"></a>CToolBarCtrl::IsButtonHighlighted  
 Проверяет состояние выделения кнопки панели инструментов.  
  
```  
BOOL IsButtonHighlighted(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды кнопки панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положительное целое число, если выделена кнопка, 0, если не выделена кнопка или -1, если ошибка возникает.  
  
##  <a name="a-nameisbuttonindeterminatea--ctoolbarctrlisbuttonindeterminate"></a><a name="isbuttonindeterminate"></a>CToolBarCtrl::IsButtonIndeterminate  
 Определяет, является ли указанный кнопки элемента управления toolbar неопределенным.  
  
```  
BOOL IsButtonIndeterminate(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положительное целое число, если кнопка находится в неопределенном состоянии нуль, если кнопка не может быть неопределенным или -1, если ошибка возникает.  
  
### <a name="remarks"></a>Примечания  
 Неопределенный кнопки отображаются серым цветом, такие, как будет выглядеть следующим образом кнопки «Полужирный» на панели инструментов текстового редактора, если выделенный текст содержит символы полужирным и обычным. Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить несколько состояний кнопки.  
  
##  <a name="a-nameisbuttonpresseda--ctoolbarctrlisbuttonpressed"></a><a name="isbuttonpressed"></a>CToolBarCtrl::IsButtonPressed  
 Определяет, нажата ли указанную кнопку в панели инструментов.  
  
```  
BOOL IsButtonPressed(int nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка нажата, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Рассмотрите возможность вызова [GetState](#getstate) Если вы хотите получить несколько состояний кнопки.  
  
##  <a name="a-nameloadimagesa--ctoolbarctrlloadimages"></a><a name="loadimages"></a>CToolBarCtrl::LoadImages  
 Загружает растровых изображений в список изображений элемента управления панели инструментов.  
  
```  
void LoadImages(
    int iBitmapID,  
    HINSTANCE hinst);
```  
  
### <a name="parameters"></a>Параметры  
 *iBitmapID*  
 Идентификатор растрового рисунка, содержащий образы загрузки. Чтобы указать ресурс точечного рисунка, присвойте этому параметру значение идентификатор ресурса растрового изображения и задайте `hInst` для **NULL**. Ресурс точечного рисунка будут добавляться в список изображений как единый образ. Можно добавлять стандартные, определяемые системой точечные рисунки, задав *hinst* для **HINST_COMMCTRL** и задайте для этого параметра в один из следующих идентификаторов:  
  
|Идентификатор растрового изображения|Описание|  
|---------------|-----------------|  
|IDB_HIST_LARGE_COLOR|Обозреватель растровых изображений большого размера|  
|IDB_HIST_SMALL_COLOR|Обозреватель точечными рисунками малого размера|  
|IDB_STD_LARGE_COLOR|Стандартная растровых изображений большого размера|  
|IDB_STD_SMALL_COLOR|Стандартная точечными рисунками малого размера|  
|IDB_VIEW_LARGE_COLOR|Представление растровых изображений большого размера|  
|IDB_VIEW_SMALL_COLOR|Представление точечными рисунками малого размера|  
  
 *hinst*  
 Дескриптор экземпляра программы вызывающему приложению. Этот параметр может иметь **HINST_COMMCTRL** для загрузки списка стандартного образа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_LOADIMAGES](http://msdn.microsoft.com/library/windows/desktop/bb787381), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemapacceleratora--ctoolbarctrlmapaccelerator"></a><a name="mapaccelerator"></a>CToolBarCtrl::MapAccelerator  
 Сопоставляет символ сочетаний клавиш для кнопки панели инструментов.  
  
```  
BOOL MapAccelerator(
    TCHAR chAccel,  
    UINT* pIDBtn);
```  
  
### <a name="parameters"></a>Параметры  
 `chAccel`  
 Ускоритель знак для сопоставления. Это тот же знак, подчеркнутый текст кнопки.  
  
 *pIDBtn*  
 Указатель на **UINT** , который получает идентификатор команды кнопки, которая соответствует сочетания клавиш, указанные в `chAccel`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_MAPACCELERATOR](http://msdn.microsoft.com/library/windows/desktop/bb787383), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemarkbuttona--ctoolbarctrlmarkbutton"></a><a name="markbutton"></a>CToolBarCtrl::MarkButton  
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
 Указывает состояние выделения задать. По умолчанию **TRUE**. Если значение **FALSE**, кнопки установлено в состояние по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_MARKBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787385), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemovebuttona--ctoolbarctrlmovebutton"></a><a name="movebutton"></a>CToolBarCtrl::MoveButton  
 Перемещение кнопки из одного индекса на другой.  
  
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
  
##  <a name="a-namepressbuttona--ctoolbarctrlpressbutton"></a><a name="pressbutton"></a>CToolBarCtrl::PressButton  
 Нажимает или отпускает указанную кнопку в панели инструментов.  
  
```  
BOOL PressButton(int nID, BOOL bPress = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды кнопки сочетание клавиш или выпуска.  
  
 [in] `bPress`  
 `true`сочетания клавиш указанную кнопку; `false` освободить указанную кнопку. Значение по умолчанию — `true`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод выполнен успешно; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите изменить более одного состояния кнопки, рассмотрите возможность вызова [SetState](#setstate) вместо.  
  
 Этот метод отправляет [TB_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb787389) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namereplacebitmapa--ctoolbarctrlreplacebitmap"></a><a name="replacebitmap"></a>CToolBarCtrl::ReplaceBitmap  
 Заменяет точечного существующего точечного рисунка в текущий элемент управления панели инструментов.  
  
```  
BOOL ReplaceBitmap(LPTBREPLACEBITMAP pReplaceBitmap);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pReplaceBitmap`|Указатель на [TBREPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb760484) структура, описывающая точечного рисунка будет заменена и новый точечный рисунок.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_REPLACEBITMAP](http://msdn.microsoft.com/library/windows/desktop/bb787391) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода заменяет другой растровый растровое изображение для стандартной панели инструментов.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_4.cpp)]  
  
##  <a name="a-namerestorestatea--ctoolbarctrlrestorestate"></a><a name="restorestate"></a>CToolBarCtrl::RestoreState  
 Восстанавливает состояние панели инструментов из расположения в реестре, указанными параметрами.  
  
```  
void RestoreState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Параметры  
 `hKeyRoot`  
 Определяет текущий открытый ключ в реестре или любой из следующих предопределенных зарезервированные дескриптора:  
  
- **РАЗДЕЛ HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **РАЗДЕЛ HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Указывает нулем строка, содержащая имя раздела, с которым связано значение. Этот параметр может иметь значение null или указатель на пустую строку. Если параметр является **NULL**, будут добавлены в раздел, идентифицируемый `hKeyRoot` параметр.  
  
 `lpszValueName`  
 Указывает строку, содержащую имя извлекаемого значения. Если значение с таким именем не существует в ключе, функция добавляет его ключ.  
  
##  <a name="a-namesavestatea--ctoolbarctrlsavestate"></a><a name="savestate"></a>CToolBarCtrl::SaveState  
 Сохраняет состояние элемента панели инструментов в расположение в реестре, указанными параметрами.  
  
```  
void SaveState(
    HKEY hKeyRoot,  
    LPCTSTR lpszSubKey,  
    LPCTSTR lpszValueName);
```  
  
### <a name="parameters"></a>Параметры  
 `hKeyRoot`  
 Определяет текущий открытый ключ в реестре или любой из следующих предопределенных зарезервированные дескриптора:  
  
- **РАЗДЕЛ HKEY_CLASSES_ROOT**  
  
- **HKEY_CURRENT_USER**  
  
- **РАЗДЕЛ HKEY_LOCAL_MACHINE**  
  
- **HKEY_USERS**  
  
 `lpszSubKey`  
 Указывает нулем строка, содержащая имя раздела, с которым связано значение. Этот параметр может иметь значение null или указатель на пустую строку. Если параметр является **NULL**, будут добавлены в раздел, идентифицируемый `hKeyRoot` параметр.  
  
 `lpszValueName`  
 Указывает строку, содержащую имя задаваемое значение. Если значение с таким именем не существует в ключе, функция добавляет его ключ.  
  
##  <a name="a-namesetanchorhighlighta--ctoolbarctrlsetanchorhighlight"></a><a name="setanchorhighlight"></a>CToolBarCtrl::SetAnchorHighlight  
 Задает привязки выделения, Настройка панели инструментов.  
  
```  
BOOL SetAnchorHighlight(BOOL fAnchor = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `fAnchor`  
 Указывает, если выделение привязка включена или отключена. Если это значение не равно нулю, будет включена привязка выделение. Если это значение равно нулю, будет отключена выделение привязки  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие настройки привязки. Если выделение было включено, это значение не равно нулю. Если выделение не включена, это значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [TB_SETANCHORHIGHLIGHT](http://msdn.microsoft.com/library/windows/desktop/bb787396), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbitmapsizea--ctoolbarctrlsetbitmapsize"></a><a name="setbitmapsize"></a>CToolBarCtrl::SetBitmapSize  
 Задает размер фактических точечных рисунков для добавления элемента управления панели инструментов.  
  
```  
BOOL SetBitmapSize(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Ширина и высота в пикселях точечных рисунков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только перед добавлением любые точечные рисунки в панели инструментов. Если приложение явно не задавать размер точечного рисунка, по умолчанию до 15, 16 пикселей.  
  
##  <a name="a-namesetbuttoninfoa--ctoolbarctrlsetbuttoninfo"></a><a name="setbuttoninfo"></a>CToolBarCtrl::SetButtonInfo  
 Задает сведения для существующей кнопки в панели инструментов.  
  
```  
BOOL SetButtonInfo(
    int nID,  
    TBBUTTONINFO* ptbbi);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор кнопки.  
  
 `ptbbi`  
 Указатель на [TBBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb760478) структуру, которая получает данные о кнопке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция-член реализует поведение сообщения Win32 [TB_SETBUTTONINFO](http://msdn.microsoft.com/library/windows/desktop/bb787413), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbuttonsizea--ctoolbarctrlsetbuttonsize"></a><a name="setbuttonsize"></a>CToolBarCtrl::SetButtonSize  
 Задает размер кнопок в панели инструментов.  
  
```  
BOOL SetButtonSize(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Ширина и высота в пикселях кнопок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Всегда необходимо по крайней мере размер точечного рисунка, он помещает размер кнопки. Эта функция должна вызываться только перед добавлением любые точечные рисунки в панели инструментов. Если приложение не задано явно размер кнопок, по умолчанию используется 24 x 22 точек.  
  
### <a name="example"></a>Пример  
  В примере показано [CToolBar::GetToolBarCtrl](../../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
##  <a name="a-namesetbuttonstructsizea--ctoolbarctrlsetbuttonstructsize"></a><a name="setbuttonstructsize"></a>CToolBarCtrl::SetButtonStructSize  
 Указывает размер `TBBUTTON` структуры.  
  
```  
void SetButtonStructSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nSize`  
 Размер в байтах для `TBBUTTON` структуры.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите хранить дополнительные данные в `TBBUTTON` структуры, можно либо создать новую структуру из `TBBUTTON`, добавление элементов вы необходимые или создать новую структуру, содержащую `TBBUTTON` структуру в качестве ее первого элемента. Затем необходимо вызвать эту функцию, чтобы определить размер новой структуры управления панели инструментов.  
  
 В разделе [CToolBarCtrl::AddButtons](#addbuttons) Дополнительные сведения о `TBBUTTON` структуры.  
  
##  <a name="a-namesetbuttonwidtha--ctoolbarctrlsetbuttonwidth"></a><a name="setbuttonwidth"></a>CToolBarCtrl::SetButtonWidth  
 Задает кнопку минимальное и максимальное значения ширины в панели инструментов.  
  
```  
BOOL SetButtonWidth(
    int cxMin,  
    int cxMax);
```  
  
### <a name="parameters"></a>Параметры  
 `cxMin`  
 Кнопка минимальные ширину в пикселях. Кнопки панели инструментов и не будет уже, чем это значение.  
  
 *cxMax*  
 Максимальное число кнопок ширина в пикселях. Текст кнопки слишком велик, элемент управления отображает с точками с многоточием.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETBUTTONWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb787417), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcmdida--ctoolbarctrlsetcmdid"></a><a name="setcmdid"></a>CToolBarCtrl::SetCmdID  
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
 Идентификатор команды для установки выбранной кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение, если выполнено успешно; в противном случае — нуль.  
  
##  <a name="a-namesetcolorschemea--ctoolbarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>CToolBarCtrl::SetColorScheme  
 Задает цвет элемента панели инструментов.  
  
```  
void SetColorScheme(const COLORSCHEME* lpColorScheme);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `lpColorScheme`|Указатель на [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) структура, описывающая цвет выделения и цвет тени панели инструментов.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод не оказывает влияния [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] задать тему.  
  
 Этот метод отправляет [TB_SETCOLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb787421) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается цветовой схемы для текущего элемента управления панели инструментов. В примере кода делает синий левому и верхнему краю каждой red кнопки инструмента и правому и нижнему краю. Когда пользователь нажимает кнопку, красной границы кнопки синим цветом и краям синий красным цветом.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_5.cpp)]  
  
##  <a name="a-namesetdisabledimagelista--ctoolbarctrlsetdisabledimagelist"></a><a name="setdisabledimagelist"></a>CToolBarCtrl::SetDisabledImageList  
 Задает список изображений, который будет использоваться элементом управления панели инструментов для отображения неактивных кнопок.  
  
```  
CImageList* SetDisabledImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения для использования с элементом управления для отображения неактивных изображений на кнопках панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, который ранее использовался элементом управления панели инструментов для отображения неактивных изображения кнопок.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETDISABLEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787423), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Реализация MFC `SetDisabledImageList` использует `CImageList` изображения объекта, содержащего отключенной кнопки панели инструментов вместо дескриптор списка изображений.  
  
##  <a name="a-namesetdrawtextflagsa--ctoolbarctrlsetdrawtextflags"></a><a name="setdrawtextflags"></a>CToolBarCtrl::SetDrawTextFlags  
 Задает флаги в функцию Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), который используется для отрисовки текста в указываемом прямоугольнике, отформатированное в соответствии со установке флагов.  
  
```  
DWORD SetDrawTextFlags(
    DWORD dwMask,  
    DWORD dwDTFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMask`  
 Сочетание одного или нескольких флагов DT_, указанный в функции Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), указывающее, что биты `dwDTFlags` будет использоваться при рисовании текста.  
  
 `dwDTFlags`  
 Сочетание одного или нескольких флагов DT_, указанный в функции Win32 `DrawText`, которые указывают, как будет отображаться на кнопке отображается надпись. Это значение передается `DrawText` при рисовании текста кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `DWORD` содержащий Рисование флаги предыдущего текста.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETDRAWTEXTFLAGS](http://msdn.microsoft.com/library/windows/desktop/bb787425), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Эта функция-член задает флаги в функцию Win32 `DrawText`, который рисует текст в указанном прямоугольнике, отформатированное в соответствии со установке флагов.  
  
##  <a name="a-namesetextendedstylea--ctoolbarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CToolBarCtrl::SetExtendedStyle  
 Задает расширенные стили для элемента управления панели инструментов.  
  
```  
DWORD SetExtendedStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Значение, задающее новые расширенные стили. Этот параметр может представлять собой сочетание расширенные стили панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` , представляющий предыдущий расширенные стили. Список стилей см. в разделе [расширенные стили панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760430)в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb787427), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesethotimagelista--ctoolbarctrlsethotimagelist"></a><a name="sethotimagelist"></a>CToolBarCtrl::SetHotImageList  
 Задает список изображений, используемый элементом управления панели инструментов для отображения кнопок «горячей».  
  
```  
CImageList* SetHotImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения, используемые элементом управления панели инструментов для отображения изображений кнопку в активном состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, который ранее использовался элементом управления панели инструментов для отображения изображений кнопку в активном состоянии.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETHOTIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787429), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Реализация MFC `SetHotImageList` использует `CImageList` объект, содержащий кнопку панели инструментов в активном состоянии образы, а не дескриптор списка изображений. Кнопку в активном состоянии выделяется, когда указатель находится над ним.  
  
##  <a name="a-namesethotitema--ctoolbarctrlsethotitem"></a><a name="sethotitem"></a>CToolBarCtrl::SetHotItem  
 Задает горячей элемента панели инструментов.  
  
```  
int SetHotItem(int nHot);
```  
  
### <a name="parameters"></a>Параметры  
 *nHot*  
 Отсчитываемый от нуля индекс элемента, который будет осуществляться горячей. Если это значение равно -1, ни один из элементов будет горячим.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс предыдущего модной или -1, если не было горячей элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETHOTITEM](http://msdn.microsoft.com/library/windows/desktop/bb787431), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--ctoolbarctrlsetimagelist"></a><a name="setimagelist"></a>CToolBarCtrl::SetImageList  
 Задает список изображений, панели инструментов будет использовать для отображения кнопок, которые находятся в состоянии по умолчанию.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий изображения, используемые элементом управления панели инструментов для отображения изображения кнопки в состоянии по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объект, который ранее использовался элементом управления панели инструментов для отображения изображения кнопки в состоянии по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787433), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Реализация MFC `SetImageList` использует `CImageList` изображения объекта, содержащего кнопки панели инструментов вместо дескриптор списка изображений.  
  
##  <a name="a-namesetindenta--ctoolbarctrlsetindent"></a><a name="setindent"></a>CToolBarCtrl::SetIndent  
 Задает отступ для первой кнопки элемента управления toolbar.  
  
```  
BOOL SetIndent(int iIndent);
```  
  
### <a name="parameters"></a>Параметры  
 *iIndent*  
 Значение, указывающее отступа, в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namesetinsertmarka--ctoolbarctrlsetinsertmark"></a><a name="setinsertmark"></a>CToolBarCtrl::SetInsertMark  
 Задает текущий знак вставки для панели инструментов.  
  
```  
void SetInsertMark(TBINSERTMARK* ptbim);
```  
  
### <a name="parameters"></a>Параметры  
 `ptbim`  
 Указатель на [TBINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb760480) структуру, содержащую знак вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb787437), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetinsertmarkcolora--ctoolbarctrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CToolBarCtrl::SetInsertMarkColor  
 Задает цвет, используемый для рисования знак вставки для панели инструментов.  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Параметры  
 `clrNew`  
 Объект **COLORREF** значение, содержащее новый цвет метки вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее на предыдущий цвет метки вставки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TB_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb787439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmaxtextrowsa--ctoolbarctrlsetmaxtextrows"></a><a name="setmaxtextrows"></a>CToolBarCtrl::SetMaxTextRows  
 Задает максимальное количество строк текста, отображаемый на кнопке панели инструментов.  
  
```  
BOOL SetMaxTextRows(int iMaxRows);
```  
  
### <a name="parameters"></a>Параметры  
 *iMaxRows*  
 Максимальное количество строк, чтобы задать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
##  <a name="a-namesetmetricsa--ctoolbarctrlsetmetrics"></a><a name="setmetrics"></a>CToolBarCtrl::SetMetrics  
 Задает метрики из `CToolBarCtrl` объекта.  
  
```  
void SetMetrics(LPTBMETRICS ptbm);
```  
  
### <a name="parameters"></a>Параметры  
 `ptbm`  
 Указатель на [TBMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb760482) структуры `CToolBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TB_SETMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb787446) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetownera--ctoolbarctrlsetowner"></a><a name="setowner"></a>CToolBarCtrl::SetOwner  
 Задает для элемента управления панели инструментов окна-владельца.  
  
```  
void SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на `CWnd` или `CWnd`-производный объект, который будет нового окна-владельца для панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Окна-владельца — это окно, получающий уведомления от панели инструментов.  
  
##  <a name="a-namesetpaddinga--ctoolbarctrlsetpadding"></a><a name="setpadding"></a>CToolBarCtrl::SetPadding  
 Задает горизонтальное и вертикальное заполнение текущего элемента управления панели инструментов.  
  
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
 A `DWORD` которого младшее слово содержит предыдущее значение заполнения горизонтальной, а которого старшее слово предыдущее значение вертикальный отступ. Заполнение значения измеряются в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_SETPADDING](http://msdn.microsoft.com/library/windows/desktop/bb787448) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается 20 пикселей горизонтальные и вертикальные заполнения текущего элемента управления панели инструментов.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_6.cpp)]  
  
##  <a name="a-namesetpressedimagelista--ctoolbarctrlsetpressedimagelist"></a><a name="setpressedimagelist"></a>CToolBarCtrl::SetPressedImageList  
 Задает список изображений, текущий элемент управления панели инструментов используется для представления кнопки в нажатом состоянии.  
  
```  
CImagelist* SetPressedImageList(
    int iImageID,   
    CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iImageID`|Отсчитываемый от нуля индекс списка изображений. Установите этот параметр равным нулю, если использовать только один список изображений.|  
|[in] `pImageList`|Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий новый список изображений.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) , содержащий список предыдущих изображения для текущего элемента управления или `NULL` Если такой список изображений не было задано.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TB_SETPRESSEDIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb787453) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает список изображений нажатом же список изображений по умолчанию.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctoolbarctrl-class_7.cpp)]  
  
##  <a name="a-namesetrowsa--ctoolbarctrlsetrows"></a><a name="setrows"></a>CToolBarCtrl::SetRows  
 Запрашивает панели инструментов для изменения размера самого запрашиваемое количество строк.  
  
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
 Указывает, следует ли использовать больше или меньше строк, если панель инструментов не может быть изменен для запрашиваемое количество строк.  
  
 `lpRect`  
 Указывает [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, получит ограничивающий прямоугольник на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Если панель инструментов не изменяет свой размер для запрошенного числа или строки, будет изменяться либо следующего большего размера или Далее меньше допустимого размера в зависимости от значения `bLarger`. Если `bLarger` — **TRUE**, новое число строк будет больше запрошенного числа. Если `bLarger` — **FALSE**, количество новых строк будет меньше запрошенного числа.  
  
 Заданное количество строк является допустимым для панели инструментов, если кнопки могут быть упорядочены таким образом, что все строки имеют одинаковое число кнопок (за исключением возможно последняя строка). Например панель инструментов, которая содержит четыре кнопки может не настраиваются в три строки, так как последние две строки будет короче. При попытке сделать его три строки, будет получена четыре строки при `bLarger` было **TRUE** и две строки, если `bLarger` было **FALSE**.  
  
 Если на панели инструментов разделители, когда заданное количество строк является действительным правила сложнее. Макет является вычисляемым, таким образом, что группы кнопок (кнопки с разделителем перед первым) и последней кнопки в группе никогда не подразделяются на несколько строк, если только группы не может поместиться на одной строке.  
  
 Если группа не помещается на одной строке, следующей группы начнет в следующей строке, даже если он поместится в строке, где заканчивается большой группы. Это правило предназначено для сделать разделение больших групп более заметно. Полученный вертикальные разделители, рассматриваются как строки.  
  
 Обратите внимание, что `SetRows` функция-член всегда будет выбран макет, который приводит к наименьший размер панели инструментов. Создание панели инструментов с `TBSTYLE_WRAPABLE` стиль и затем размера элемента управления просто примените метода, описанного выше заданного ширину элемента управления.  
  
 Эта функция может вызываться только для панели инструментов, которые были созданы с помощью `TBSTYLE_WRAPABLE` стиль.  
  
##  <a name="a-namesetstatea--ctoolbarctrlsetstate"></a><a name="setstate"></a>CToolBarCtrl::SetState  
 Задает состояние для указанной кнопки в панели инструментов.  
  
```  
BOOL SetState(
    int nID,  
    UINT nState);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор команды кнопки.  
  
 `nState`  
 Флаги состояния. Он может быть сочетания значений, указанных для состояний кнопки в [CToolBarCtrl::AddButtons](#addbuttons).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция особенно полезна, если требуется задать более чем одно из состояний кнопки. Просто установите для одного состояния, используйте один из следующих функций-членов: [EnableButton](#enablebutton), [CheckButton](#checkbutton), [HideButton](#hidebutton), [неопределенный](#indeterminate), или [PressButton](#pressbutton).  
  
##  <a name="a-namesetstylea--ctoolbarctrlsetstyle"></a><a name="setstyle"></a>CToolBarCtrl::SetStyle  
 Задает стили для элемента управления панели инструментов.  
  
```  
void SetStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Объект `DWORD` содержащий сочетание [стили элемента управления панели инструментов](http://msdn.microsoft.com/library/windows/desktop/bb760439), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettooltipsa--ctoolbarctrlsettooltips"></a><a name="settooltips"></a>CToolBarCtrl::SetToolTips  
 Связывает управления всплывающей подсказки с элементом управления панели инструментов.  
  
```  
void SetToolTips(CToolTipCtrl* pTip);
```  
  
### <a name="parameters"></a>Параметры  
 *pTip*  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта.  
  
##  <a name="a-namesetwindowthemea--ctoolbarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolBarCtrl::SetWindowTheme  
 Задает стиль оформления `CToolBarCtrl` объекта.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержащий инструментов визуального стиля.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb787465) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Пример MFC MFCIE](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBar-класс](../../mfc/reference/ctoolbar-class.md)

