---
title: "Класс CWindow | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CWindow
- ATL::CWindow
- CWindow
dev_langs:
- C++
helpviewer_keywords:
- CWindow class
ms.assetid: fefa00c8-f053-4bcf-87bc-dc84f5386683
caps.latest.revision: 21
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
ms.openlocfilehash: dd5e052f74fad8362c58170262e4229549e26868
ms.lasthandoff: 02/24/2017

---
# <a name="cwindow-class"></a>Класс CWindow
Этот класс предоставляет методы для управления окном.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CWindow
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindow::CWindow](#cwindow)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindow::ArrangeIconicWindows](#arrangeiconicwindows)|Упорядочивает все дочерние свернутого окна.|  
|[CWindow::Attach](#attach)|Присоединяет окно `CWindow` объекта.|  
|[CWindow::BeginPaint](#beginpaint)|Подготавливает окна для рисования.|  
|[CWindow::BringWindowToTop](#bringwindowtotop)|Выводит окно в начало Z-порядка.|  
|[CWindow::CenterWindow](#centerwindow)|Выравнивает окно для данного окна.|  
|[CWindow::ChangeClipboardChain](#changeclipboardchain)|Удаляет окно из цепочки средства просмотра буфера обмена.|  
|[CWindow::CheckDlgButton](#checkdlgbutton)|Изменяет состояние флажка указанную кнопку.|  
|[CWindow::CheckRadioButton](#checkradiobutton)|Проверяет указанный переключатель.|  
|[CWindow::ChildWindowFromPoint](#childwindowfrompoint)|Возвращает дочернее окно, содержащее указанную точку.|  
|[CWindow::ChildWindowFromPointEx](#childwindowfrompointex)|Возвращает определенный тип дочернего окна, содержащего заданную точку.|  
|[CWindow::ClientToScreen](#clienttoscreen)|Преобразует клиентских координат в экранные координаты.|  
|[CWindow::Create](#create)|Создает окно.|  
|[CWindow::CreateCaret](#createcaret)|Создает новую форму системного курсора.|  
|[CWindow::CreateGrayCaret](#creategraycaret)|Создает серый прямоугольник для системного курсора.|  
|[CWindow::CreateSolidCaret](#createsolidcaret)|Создает сплошной прямоугольник для системного курсора.|  
|[CWindow::DeferWindowPos](#deferwindowpos)|Обновляет указанной структуры нескольких положение окна для указанного окна.|  
|[CWindow::DestroyWindow](#destroywindow)|Уничтожает окно, связанное с `CWindow` объекта.|  
|[CWindow::Detach](#detach)|Отсоединяет в окне `CWindow` объекта.|  
|[CWindow::DlgDirList](#dlgdirlist)|Заполняет поле со списком имена всех файлов, соответствующих указанному пути или имени файла.|  
|[CWindow::DlgDirListComboBox](#dlgdirlistcombobox)|Заполняет поле со списком имена всех файлов, соответствующих указанному пути или имени файла.|  
|[CWindow::DlgDirSelect](#dlgdirselect)|Извлекает текущее выделение из списка.|  
|[CWindow::DlgDirSelectComboBox](#dlgdirselectcombobox)|Получает текущее выделение в поле со списком.|  
|[CWindow::DragAcceptFiles](#dragacceptfiles)|Регистры, принимает ли окно перетащить файлы.|  
|[CWindow::DrawMenuBar](#drawmenubar)|Перерисовывает меню окна.|  
|[CWindow::EnableScrollBar](#enablescrollbar)|Включает или отключает стрелку полосы прокрутки.|  
|[CWindow::EnableWindow](#enablewindow)|Включает или отключает возможность ввода данных.|  
|[CWindow::EndPaint](#endpaint)|Отмечает завершение рисования.|  
|[CWindow::FlashWindow](#flashwindow)|Окно однократно мигает.|  
|[CWindow::GetClientRect](#getclientrect)|Возвращает координаты клиентской области.|  
|[CWindow::GetDC](#getdc)|Получает контекст устройства для клиентской области.|  
|[CWindow::GetDCEx](#getdcex)|Получает контекст устройства для клиентской области и с помощью этих параметров обрезки.|  
|[CWindow::GetDescendantWindow](#getdescendantwindow)|Возвращает потомков указанного окна.|  
|[CWindow::GetDlgControl](#getdlgcontrol)|Получает интерфейс для указанного элемента управления.|  
|[CWindow::GetDlgCtrlID](#getdlgctrlid)|Извлекает идентификатор окна (для дочерних окон).|  
|[CWindow::GetDlgHost](#getdlghost)|Извлекает указатель на интерфейс для управления ATL, размещение контейнера.|  
|[CWindow::GetDlgItem](#getdlgitem)|Возвращает указанное дочернее окно.|  
|[CWindow::GetDlgItemInt](#getdlgitemint)|Преобразует текст элемента управления в целое число.|  
|[CWindow::GetDlgItemText](#getdlgitemtext)|Извлекает текст элемента управления.|  
|[CWindow::GetExStyle](#getexstyle)|Извлекает расширенные стили окна.|  
|[CWindow::GetFont](#getfont)|Извлекает текущий шрифт окна.|  
|[CWindow::GetHotKey](#gethotkey)|Определяет сочетания клавиш, связанных с этим окном.|  
|[CWindow::GetIcon](#geticon)|Извлекает окно крупных или мелких значков.|  
|[CWindow::GetLastActivePopup](#getlastactivepopup)|Возвращает последнюю активную всплывающего окна.|  
|[CWindow::GetMenu](#getmenu)|Извлекает меню окна.|  
|[CWindow::GetNextDlgGroupItem](#getnextdlggroupitem)|Возвращает предыдущий или следующий элемент управления в группе элементов управления.|  
|[CWindow::GetNextDlgTabItem](#getnextdlgtabitem)|Извлекает наличие предыдущего или следующего элемента управления **WS_TABSTOP** стиль.|  
|[CWindow::GetParent](#getparent)|Получает непосредственный родительский окна.|  
|[CWindow::GetScrollInfo](#getscrollinfo)|Извлекает параметры полосы прокрутки.|  
|[CWindow::GetScrollPos](#getscrollpos)|Получает положение ползунка полосы прокрутки.|  
|[CWindow::GetScrollRange](#getscrollrange)|Возвращает диапазон значений для полосы прокрутки.|  
|[CWindow::GetStyle](#getstyle)|Получает стили окна.|  
|[CWindow::GetSystemMenu](#getsystemmenu)|Создает копию объекта меню системы для изменения.|  
|[CWindow::GetTopLevelParent](#gettoplevelparent)|Получает окно верхнего уровня родительского или владельца.|  
|[CWindow::GetTopLevelWindow](#gettoplevelwindow)|Получает окно верхнего уровня владельца.|  
|[CWindow::GetTopWindow](#gettopwindow)|Возвращает дочернее окно верхнего уровня.|  
|[CWindow::GetUpdateRect](#getupdaterect)|Возвращает координаты наименьший прямоугольник, ограничивающий область обновления полностью.|  
|[CWindow::GetUpdateRgn](#getupdatergn)|Получает область обновления и копирует их в заданной области.|  
|[CWindow::GetWindow](#getwindow)|Извлекает заданное окно.|  
|[CWindow::GetWindowContextHelpId](#getwindowcontexthelpid)|Получает идентификатор контекста справки окна.|  
|[CWindow::GetWindowDC](#getwindowdc)|Получает контекст устройства для всего содержимого окна.|  
|[CWindow::GetWindowLong](#getwindowlong)|Получает 32-разрядное значение с указанным смещением в открытое окно память.|  
|[CWindow::GetWindowLongPtr](#getwindowlongptr)|Извлекает сведения о указанного окна, включая значение с указанным смещением в открытое окно память.|  
|[CWindow::GetWindowPlacement](#getwindowplacement)|Извлекает show state и позиций.|  
|[CWindow::GetWindowProcessID](#getwindowprocessid)|Извлекает идентификатор процесса, который окно создал.|  
|[CWindow::GetWindowRect](#getwindowrect)|Возвращает ограничивающий размеры окна.|  
|[CWindow::GetWindowRgn](#getwindowrgn)|Получает копию этой области окна.|  
|[CWindow::GetWindowText](#getwindowtext)|Извлекает текст окна.|  
|[CWindow::GetWindowTextLength](#getwindowtextlength)|Получает длину текстового окна.|  
|[CWindow::GetWindowThreadID](#getwindowthreadid)|Получает идентификатор потока, который создал указанного окна.|  
|[CWindow::GetWindowWord](#getwindowword)|Возвращает 16-разрядное значение с указанным смещением в открытое окно память.|  
|[CWindow::GotoDlgCtrl](#gotodlgctrl)|Устанавливает фокус на элемент управления в диалоговом окне.|  
|[CWindow::HideCaret](#hidecaret)|Скрывает курсор системы.|  
|[CWindow::HiliteMenuItem](#hilitemenuitem)|Выделяет или снимает выделение с меню верхнего уровня.|  
|[CWindow::Invalidate](#invalidate)|Делает недействительной всю клиентскую область.|  
|[CWindow::InvalidateRect](#invalidaterect)|Делает недействительной клиентской области в заданном прямоугольнике.|  
|[CWindow::InvalidateRgn](#invalidatergn)|Делает недействительной клиентской области в пределах указанной области.|  
|[CWindow::IsChild](#ischild)|Определяет, является ли заданное окно дочернего окна.|  
|[CWindow::IsDialogMessage](#isdialogmessage)|Определяет, является ли сообщение предназначено для указанного диалогового.|  
|[CWindow::IsDlgButtonChecked](#isdlgbuttonchecked)|Определяет состояние флажка кнопки.|  
|[CWindow::IsIconic](#isiconic)|Определяет, свернута ли окно.|  
|[CWindow::IsParentDialog](#isparentdialog)|Определяет, является ли родительского окна элемента управления, появится диалоговое окно.|  
|[CWindow::IsWindow](#iswindow)|Определяет, является ли заданный дескриптор окна определяет существующее окно.|  
|[CWindow::IsWindowEnabled](#iswindowenabled)|Определяет, включен ли окно для ввода данных.|  
|[CWindow::IsWindowUnicode](#iswindowunicode)|Определяет, является ли заданное окно собственного окна Юникода.|  
|[CWindow::IsWindowVisible](#iswindowvisible)|Определяет состояние видимость окна.|  
|[CWindow::IsZoomed](#iszoomed)|Определяет, является ли окно развернуто.|  
|[CWindow::KillTimer](#killtimer)|Уничтожает событие таймера.|  
|[CWindow::LockWindowUpdate](#lockwindowupdate)|Отключает или включает рисования в окне.|  
|[CWindow::MapWindowPoints](#mapwindowpoints)|Преобразует набор точек из координат окна пространства координат в другом окне.|  
|[CWindow::MessageBox](#messagebox)|Отображает окно сообщения.|  
|[CWindow::ModifyStyle](#modifystyle)|Изменение стилей окна.|  
|[CWindow::ModifyStyleEx](#modifystyleex)|Изменяет расширенные стили окна.|  
|[CWindow::MoveWindow](#movewindow)|Изменяет размер и положение окна.|  
|[CWindow::NextDlgCtrl](#nextdlgctrl)|Устанавливает фокус на следующий элемент управления в диалоговом окне.|  
|[CWindow::OpenClipboard](#openclipboard)|Открывает буфер обмена.|  
|[CWindow::PostMessage](#postmessage)|Помещает сообщение в очередь сообщений, связанных с потоком, создавший окно. Возвращает значение, не ждет поток для обработки сообщения.|  
|[CWindow::PrevDlgCtrl](#prevdlgctrl)|Устанавливает фокус на предыдущий элемент управления в диалоговом окне.|  
|[CWindow::Print](#print)|Запросы, что окна должен выводиться в контексте указанного устройства.|  
|[CWindow::PrintClient](#printclient)|Запросы, в заданный контекст устройства изображать клиентской области окна.|  
|[CWindow::RedrawWindow](#redrawwindow)|Обновляет указанный прямоугольник или область в клиентской области.|  
|[CWindow::ReleaseDC](#releasedc)|Освобождает контекст устройства.|  
|[CWindow::ResizeClient](#resizeclient)|Изменяет размер окна.|  
|[CWindow::ScreenToClient](#screentoclient)|Преобразует координат экрана в клиентских координатах.|  
|[CWindow::ScrollWindow](#scrollwindow)|Прокручивает указанной клиентской области.|  
|[CWindow::ScrollWindowEx](#scrollwindowex)|Прокручивает указанной клиентской области с дополнительными возможностями.|  
|[CWindow::SendDlgItemMessage](#senddlgitemmessage)|Отправляет сообщение в элемент управления.|  
|[CWindow::SendMessage](#sendmessage)|Отправляет сообщение в окно и не возвращается, пока не обработал сообщение процедуре окна.|  
|[CWindow::SendMessageToDescendants](#sendmessagetodescendants)|Отправляет сообщение на указанный окон-потомков.|  
|[CWindow::SendNotifyMessage](#sendnotifymessage)|Отправляет сообщение в окно. Если окно было создано вызывающим потоком `SendNotifyMessage` не возвращается, пока не обработал сообщение процедуре окна. В противном случае возвращается немедленно.|  
|[CWindow::SetActiveWindow](#setactivewindow)|Активирует окно.|  
|[CWindow::SetCapture](#setcapture)|Отправляет все последующие мыши в окне.|  
|[CWindow::SetClipboardViewer](#setclipboardviewer)|Добавляет окно в цепочку просмотра буфера обмена.|  
|[CWindow::SetDlgCtrlID](#setdlgctrlid)|Изменяет идентификатор окна.|  
|[CWindow::SetDlgItemInt](#setdlgitemint)|Изменяет текст элемента управления в строковое представление целого числа.|  
|[CWindow::SetDlgItemText](#setdlgitemtext)|Изменение текста элемента управления.|  
|[CWindow::SetFocus](#setfocus)|Устанавливает фокус ввода в окно.|  
|[CWindow::SetFont](#setfont)|Изменяет текущий шрифт окна.|  
|[CWindow::SetHotKey](#sethotkey)|Связывает сочетания клавиш с окном.|  
|[CWindow::SetIcon](#seticon)|Изменяет окна крупных или мелких значков.|  
|[CWindow::SetMenu](#setmenu)|Изменяет текущее меню окна.|  
|[CWindow::SetParent](#setparent)|Изменяет родительское окно.|  
|[CWindow::SetRedraw](#setredraw)|Устанавливает или снимает флаг перерисовки.|  
|[CWindow::SetScrollInfo](#setscrollinfo)|Задает параметры полосы прокрутки.|  
|[CWindow::SetScrollPos](#setscrollpos)|Изменение положения ползунка полосы прокрутки.|  
|[CWindow::SetScrollRange](#setscrollrange)|Изменяет диапазон значений для полосы прокрутки.|  
|[CWindow::SetTimer](#settimer)|Создает событие таймера.|  
|[CWindow::SetWindowContextHelpId](#setwindowcontexthelpid)|Задает идентификатор контекста справки окна.|  
|[CWindow::SetWindowLong](#setwindowlong)|Задает 32-разрядное значение с указанным смещением в память открытое окно.|  
|[CWindow::SetWindowLongPtr](#setwindowlongptr)|Изменяет атрибут указанного окна, а также задает значение с указанным смещением в открытое окно памяти.|  
|[CWindow::SetWindowPlacement](#setwindowplacement)|Задает состояние отображения и положения.|  
|[CWindow::SetWindowPos](#setwindowpos)|Задает размер, положение и Z-порядку.|  
|[CWindow::SetWindowRgn](#setwindowrgn)|Задает область окна, окна.|  
|[CWindow::SetWindowText](#setwindowtext)|Изменяет текст окна.|  
|[CWindow::SetWindowWord](#setwindowword)|Задает 16-разрядное значение с указанным смещением в открытое окно память.|  
|[CWindow::ShowCaret](#showcaret)|Отображает системного курсора.|  
|[CWindow::ShowOwnedPopups](#showownedpopups)|Показывает или скрывает всплывающие окна, принадлежащие окна.|  
|[CWindow::ShowScrollBar](#showscrollbar)|Показывает или скрывает полосы прокрутки.|  
|[CWindow::ShowWindow](#showwindow)|Задает состояние окна отображения.|  
|[CWindow::ShowWindowAsync](#showwindowasync)|Задает состояние отображения окна, созданного в другом потоке.|  
|[CWindow::UpdateWindow](#updatewindow)|Обновляет клиентскую область.|  
|[CWindow::ValidateRect](#validaterect)|Проверяет клиентской области в заданном прямоугольнике.|  
|[CWindow::ValidateRgn](#validatergn)|Проверяет клиентской области в пределах указанной области.|  
|[CWindow::WinHelp](#winhelp)|Запускает справку Windows.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindow::operator HWND](#operator_hwnd)|Преобразует `CWindow` объект `HWND`.|  
|[CWindow::operator =](#operator_eq)|Назначает `HWND` для `CWindow` объектов.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindow::m_hWnd](#m_hwnd)|Дескриптор окна, связанный с `CWindow` объекта.|  
|[CWindow::rcDefault](#rcdefault)|Содержит размеры окна по умолчанию.|  
  
## <a name="remarks"></a>Примечания  
 `CWindow`Предоставляет базовую функциональность для управления окном в ATL. Многие `CWindow` методы просто перенести одну из функций интерфейса Win32 API. Например, сравните прототипы для `CWindow::ShowWindow` и `ShowWindow`:  
  
|Метод CWindow|Функция Win32|  
|--------------------|--------------------|  
|**BOOL ShowWindow (int** `nCmdShow` **);**|**BOOL ShowWindow( HWND** `hWnd` **, int** `nCmdShow` **);**|  
  
 `CWindow::ShowWindow`вызывает функцию Win32 `ShowWindow` , передав `CWindow::m_hWnd` как первый параметр. Каждый `CWindow` передает в метод, который непосредственно создает оболочку для функции Win32 `m_hWnd` член класса, поэтому большая часть `CWindow` документации содержит ссылку на [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Является оболочкой для функции Win32 не все связанные с окном `CWindow`, а не каждому `CWindow` метод создает оболочку для функции Win32.  
  
 `CWindow::m_hWnd`хранит `HWND` , определяющий окно. `HWND` Присоединяется к объекту при вы:  
  
-   Укажите `HWND` в `CWindow`в конструктор.  
  
-   Вызовите метод `CWindow::Attach`.  
  
-   Use `CWindow`'s **operator =**.  
  
-   Создание или подкласс окна с помощью одного из следующих классов, производный от `CWindow`:  
  
 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) позволяет создать новое окно или подкласс существующее окно.  
  
 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) реализует окно, содержатся внутри другого объекта. Существующее окно можно создать новое окно или подкласс.  
  
 [CDialogImpl](../../atl/reference/cdialogimpl-class.md) позволяет создать модальное или немодальное диалоговое окно.  
  
 Дополнительные сведения об окнах см. в разделе [Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) и последующие разделы в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="a-namearrangeiconicwindowsa--cwindowarrangeiconicwindows"></a><a name="arrangeiconicwindows"></a>CWindow::ArrangeIconicWindows  
 Упорядочивает все дочерние свернутого окна.  
  
```
UINT ArrangeIconicWindows() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ArrangeIconicWindows](http://msdn.microsoft.com/library/windows/desktop/ms632671) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameattacha--cwindowattach"></a><a name="attach"></a>CWindow::Attach  
 Присоединяет окна определяется `hWndNew` для `CWindow` объектов.  
  
```
void Attach(HWND hWndNew) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hWndNew`  
 [in] Дескриптор окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#1;](../../atl/codesnippet/cpp/cwindow-class_1.cpp)]  
  
##  <a name="a-namebeginpainta--cwindowbeginpaint"></a><a name="beginpaint"></a>CWindow::BeginPaint  
 Подготавливает окна для рисования.  
  
```
HDC BeginPaint(LPPAINTSTRUCT lpPaint) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#2;](../../atl/codesnippet/cpp/cwindow-class_2.cpp)]  
  
##  <a name="a-namebringwindowtotopa--cwindowbringwindowtotop"></a><a name="bringwindowtotop"></a>CWindow::BringWindowToTop  
 Выводит окно в начало Z-порядка.  
  
```
BOOL BringWindowToTop() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [BringWindowToTop](http://msdn.microsoft.com/library/windows/desktop/ms632673) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#3;](../../atl/codesnippet/cpp/cwindow-class_3.cpp)]  
  
##  <a name="a-namecenterwindowa--cwindowcenterwindow"></a><a name="centerwindow"></a>CWindow::CenterWindow  
 Выравнивает окно для данного окна.  
  
```
BOOL CenterWindow(HWND hWndCenter = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hWndCenter`  
 [in] Дескриптор окна, для которого по центру. Если этот параметр равен **NULL** (значение по умолчанию), метод установит `hWndCenter` для родительского окна при дочернего окна. В противном случае, оно будет значение `hWndCenter` для окна владельца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если окно по центру успешно, в противном случае — **FALSE**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#4;](../../atl/codesnippet/cpp/cwindow-class_4.cpp)]  
  
##  <a name="a-namechangeclipboardchaina--cwindowchangeclipboardchain"></a><a name="changeclipboardchain"></a>CWindow::ChangeClipboardChain  
 Удаляет окно из цепочки средства просмотра буфера обмена.  
  
```
BOOL ChangeClipboardChain(HWND hWndNewNext) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ChangeClipboardChain](http://msdn.microsoft.com/library/windows/desktop/ms649034) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecheckdlgbuttona--cwindowcheckdlgbutton"></a><a name="checkdlgbutton"></a>CWindow::CheckDlgButton  
 Изменяет состояние флажка указанную кнопку.  
  
```
BOOL CheckDlgButton(int nIDButton, UINT nCheck) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CheckDlgButton](http://msdn.microsoft.com/library/windows/desktop/bb761875) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecheckradiobuttona--cwindowcheckradiobutton"></a><a name="checkradiobutton"></a>CWindow::CheckRadioButton  
 Проверяет указанный переключатель.  
  
```
BOOL CheckRadioButton(  
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CheckRadioButton](http://msdn.microsoft.com/library/windows/desktop/bb761877) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namechildwindowfrompointa--cwindowchildwindowfrompoint"></a><a name="childwindowfrompoint"></a>CWindow::ChildWindowFromPoint  
 Возвращает дочернее окно, содержащее указанную точку.  
  
```
HWND ChildWindowFromPoint(POINT point) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ChildWindowFromPoint](http://msdn.microsoft.com/library/windows/desktop/ms632676) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namechildwindowfrompointexa--cwindowchildwindowfrompointex"></a><a name="childwindowfrompointex"></a>CWindow::ChildWindowFromPointEx  
 Возвращает определенный тип дочернего окна, содержащего заданную точку.  
  
```
HWND ChildWindowFromPoint(POINT point, UINT uFlags) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ChildWindowFromPointEx](http://msdn.microsoft.com/library/windows/desktop/ms632677) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameclienttoscreena--cwindowclienttoscreen"></a><a name="clienttoscreen"></a>CWindow::ClientToScreen  
 Преобразует клиентских координат в экранные координаты.  
  
```
BOOL ClientToScreen(LPPOINT lpPoint) const throw();
BOOL ClientToScreen(LPRECT lpRect) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ClientToScreen](http://msdn.microsoft.com/library/windows/desktop/dd183434) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Вторая версия этого метода позволяет преобразовать координаты [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
##  <a name="a-namecreatea--cwindowcreate"></a><a name="create"></a>CWindow::Create  
 Создает окно.  
  
```
HWND Create(
    LPCTSTR lpstrWndClass,
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpstrWndClass`  
 [in] Указатель на класс окна.  
  
 `hWndParent`  
 [in] Дескриптор окна родительского или владельца.  
  
 `rect`  
 [in] Переменная типа [_U_RECT](../../atl/reference/u-rect-class.md) указание положения окна. Значение по умолчанию — **NULL**. Если этот параметр является **NULL**, значение `CWindow::rcDefault` используется.  
  
 `szWindowName`  
 [in] Задает имя окна. Значение по умолчанию — **NULL**.  
  
 `dwStyle`  
 [in] Стиль окна. Значение по умолчанию равно 0, то есть стиль не указан. Список возможных значений см. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Стиль окна расширенного. Значение по умолчанию равно 0, то есть без расширенного стиля указано. Список возможных значений см. в разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Переменная типа [_U_MENUorID](../../atl/reference/u-menuorid-class.md) указания дескриптора меню или идентификатор окна. Значение по умолчанию — 0U.  
  
 `lpCreateParam`  
 Указатель на создание окна данных, содержащихся в [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор вновь созданного окна, заданный [m_hWnd](#m_hwnd). В противном случае — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 `CWindow::rcDefault`определяется как `__declspec(selectany) RECT CWindow::rcDefault = {CW_USEDEFAULT, CW_USEDEFAULT, 0, 0};`.  
  
 В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
 **Примечание** Если 0 служит значением для `MenuOrID` параметр, он должен быть указан как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.  
  
##  <a name="a-namecreatecareta--cwindowcreatecaret"></a><a name="createcaret"></a>CWindow::CreateCaret  
 Создает новую форму системного курсора.  
  
```
BOOL CreateCaret(HBITMAP pBitmap) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CreateCaret](http://msdn.microsoft.com/library/windows/desktop/ms648399) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreategraycareta--cwindowcreategraycaret"></a><a name="creategraycaret"></a>CWindow::CreateGrayCaret  
 Создает серый прямоугольник для системного курсора.  
  
```
BOOL CreateGrayCaret(int nWidth, int nHeight) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CreateCaret](http://msdn.microsoft.com/library/windows/desktop/ms648399) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Передает (HBITMAP) 1 для битовой карты дескриптор параметра для функции Win32.  
  
##  <a name="a-namecreatesolidcareta--cwindowcreatesolidcaret"></a><a name="createsolidcaret"></a>CWindow::CreateSolidCaret  
 Создает сплошной прямоугольник для системного курсора.  
  
```
BOOL CreateSolidCaret(int nWidth, int nHeight) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CreateCaret](http://msdn.microsoft.com/library/windows/desktop/ms648399) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Передает (HBITMAP) 0 для битовой карты дескриптор параметра для функции Win32.  
  
##  <a name="a-namecwindowa--cwindowcwindow"></a><a name="cwindow"></a>CWindow::CWindow  
 Конструктор.  
  
```
CWindow(HWND hWnd = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 [in] Дескриптор окна.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует [m_hWnd](#m_hwnd) члена `hWnd`, по умолчанию — **NULL**.  
  
> [!NOTE]
> `CWindow::CWindow`не удалось создать окно. Классы [CWindowImpl](../../atl/reference/cwindowimpl-class.md), [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md), и [CDialogImpl](../../atl/reference/cdialogimpl-class.md) (все они являются производными от `CWindow`) предоставляет метод для создания окна или диалогового окна, которой затем назначается `CWindow::m_hWnd`. Можно также использовать [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) функции Win32.  
  
##  <a name="a-namedeferwindowposa--cwindowdeferwindowpos"></a><a name="deferwindowpos"></a>CWindow::DeferWindowPos  
 Обновляет указанной структуры нескольких положение окна для указанного окна.  
  
```
HDWP DeferWindowPos(  
    HDWP hWinPosInfo,
    HWND hWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT uFlags) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632681) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedestroywindowa--cwindowdestroywindow"></a><a name="destroywindow"></a>CWindow::DestroyWindow  
 Уничтожает окно, связанное с `CWindow` и устанавливает [m_hWnd](#m_hwnd) для **NULL**.  
  
```
BOOL DestroyWindow() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Она не удаляет `CWindow` сам объект.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#5;](../../atl/codesnippet/cpp/cwindow-class_5.cpp)]  
  
##  <a name="a-namedetacha--cwindowdetach"></a><a name="detach"></a>CWindow::Detach  
 Отсоединяет [m_hWnd](#m_hwnd) из `CWindow` и устанавливает `m_hWnd` для **NULL**.  
  
```
HWND Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HWND` Связанных с `CWindow` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing №&6;](../../atl/codesnippet/cpp/cwindow-class_6.cpp)]  
  
##  <a name="a-namedlgdirlista--cwindowdlgdirlist"></a><a name="dlgdirlist"></a>CWindow::DlgDirList  
 Заполняет поле со списком имена всех файлов, соответствующих указанному пути или имени файла.  
  
```
int DlgDirList(  
    LPTSTR lpPathSpec,
    int nIDListBox,
    int nIDStaticPath,
    UINT nFileType) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DlgDirList](http://msdn.microsoft.com/library/windows/desktop/bb761366) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedlgdirlistcomboboxa--cwindowdlgdirlistcombobox"></a><a name="dlgdirlistcombobox"></a>CWindow::DlgDirListComboBox  
 Заполняет поле со списком имена всех файлов, соответствующих указанному пути или имени файла.  
  
```
int DlgDirListComboBox(  
    LPTSTR lpPathSpec,
    int nIDComboBox,
    int nIDStaticPath,
    UINT nFileType) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DlgDirListComboBox](http://msdn.microsoft.com/library/windows/desktop/bb775935) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedlgdirselecta--cwindowdlgdirselect"></a><a name="dlgdirselect"></a>CWindow::DlgDirSelect  
 Извлекает текущее выделение из списка.  
  
```
BOOL DlgDirSelect(  
    LPTSTR lpString,
    int nCount,
    int nIDListBox) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DlgDirSelectEx](http://msdn.microsoft.com/library/windows/desktop/bb761368) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedlgdirselectcomboboxa--cwindowdlgdirselectcombobox"></a><a name="dlgdirselectcombobox"></a>CWindow::DlgDirSelectComboBox  
 Получает текущее выделение в поле со списком.  
  
```
BOOL DlgDirSelectComboBox(  
    LPTSTR lpString,
    int nCount,
    int nIDComboBox) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DlgDirSelectComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775937) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedragacceptfilesa--cwindowdragacceptfiles"></a><a name="dragacceptfiles"></a>CWindow::DragAcceptFiles  
 Регистры, принимает ли окно перетащить файлы.  
  
```
void DragAcceptFiles(BOOL bAccept = TRUE);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DragAcceptFiles](http://msdn.microsoft.com/library/windows/desktop/bb776406) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedrawmenubara--cwindowdrawmenubar"></a><a name="drawmenubar"></a>CWindow::DrawMenuBar  
 Перерисовывает меню окна.  
  
```
BOOL DrawMenuBar() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [DrawMenuBar](http://msdn.microsoft.com/library/windows/desktop/ms647633) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenablescrollbara--cwindowenablescrollbar"></a><a name="enablescrollbar"></a>CWindow::EnableScrollBar  
 Включает или отключает стрелку полосы прокрутки.  
  
```
BOOL EnableScrollBar(UINT uSBFlags, UINT uArrowFlags = ESB_ENABLE_BOTH) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [EnableScrollBar](http://msdn.microsoft.com/library/windows/desktop/bb787579) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenablewindowa--cwindowenablewindow"></a><a name="enablewindow"></a>CWindow::EnableWindow  
 Включает или отключает возможность ввода данных.  
  
```
BOOL EnableWindow(BOOL bEnable = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [EnableWindow](http://msdn.microsoft.com/library/windows/desktop/ms646291) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#7;](../../atl/codesnippet/cpp/cwindow-class_7.cpp)]  
  
##  <a name="a-nameendpainta--cwindowendpaint"></a><a name="endpaint"></a>CWindow::EndPaint  
 Отмечает завершение рисования.  
  
```
void EndPaint(LPPAINTSTRUCT lpPaint) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [EndPaint](http://msdn.microsoft.com/library/windows/desktop/dd162598) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#2;](../../atl/codesnippet/cpp/cwindow-class_2.cpp)]  
  
##  <a name="a-nameflashwindowa--cwindowflashwindow"></a><a name="flashwindow"></a>CWindow::FlashWindow  
 Окно однократно мигает.  
  
```
BOOL FlashWindow(BOOL bInvert) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [FlashWindow](http://msdn.microsoft.com/library/windows/desktop/ms679346) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetclientrecta--cwindowgetclientrect"></a><a name="getclientrect"></a>CWindow::GetClientRect  
 Возвращает координаты клиентской области.  
  
```
BOOL GetClientRect(LPRECT lpRect) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [метода GetClientRect](http://msdn.microsoft.com/library/windows/desktop/ms633503) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing №&8;](../../atl/codesnippet/cpp/cwindow-class_8.cpp)]  
  
##  <a name="a-namegetdca--cwindowgetdc"></a><a name="getdc"></a>CWindow::GetDC  
 Получает контекст устройства для клиентской области.  
  
```
HDC GetDC() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing №&9;](../../atl/codesnippet/cpp/cwindow-class_9.cpp)]  
  
##  <a name="a-namegetdcexa--cwindowgetdcex"></a><a name="getdcex"></a>CWindow::GetDCEx  
 Получает контекст устройства для клиентской области и с помощью этих параметров обрезки.  
  
```
HDC GetDCEx(HRGN hRgnClip, DWORD flags) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetDCEx](http://msdn.microsoft.com/library/windows/desktop/dd144873) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdescendantwindowa--cwindowgetdescendantwindow"></a><a name="getdescendantwindow"></a>CWindow::GetDescendantWindow  
 Поиск потомков окном, заданным по заданному идентификатору.  
  
```
HWND GetDescendantWindow(int nID) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 [in] Дочерние окна, чтобы получить идентификатор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна потомков.  
  
### <a name="remarks"></a>Примечания  
 `GetDescendantWindow`ищет все дерево дочерних окон, а не только windows, которые являются непосредственными дочерними элементами.  
  
##  <a name="a-namegetdlgcontrola--cwindowgetdlgcontrol"></a><a name="getdlgcontrol"></a>CWindow::GetDlgControl  
 Эта функция вызывается для получения указателя интерфейса элемента управления ActiveX, размещенный по составного элемента управления или размещение элементов управления диалогового окна.  
  
```
HRESULT GetDlgControl(  
    int nID,
    REFIID iid,
    void** ppCtrl) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 [in] Идентификатор ресурса, извлекаемого элемента управления.  
  
 `iid`  
 [in] Идентификатор интерфейса, который вы хотите получить от элемента управления.  
  
 *ppCtrl*  
 [out] Указатель на интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или любой допустимый ошибки `HRESULT`. Например, функция возвращает **E_FAIL** , если элемент управления, заданный `nID` не удается найти и возвращает **E_NOINTERFACE** Если элемент управления можно найти, но он не поддерживает интерфейс, указанный `iid`.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель можно вызывать методы интерфейса.  
  
##  <a name="a-namegetdlgctrlida--cwindowgetdlgctrlid"></a><a name="getdlgctrlid"></a>CWindow::GetDlgCtrlID  
 Извлекает идентификатор окна (для дочерних окон).  
  
```
int GetDlgCtrlID() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetDlgCtrlID](http://msdn.microsoft.com/library/windows/desktop/ms645478) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdlghosta--cwindowgetdlghost"></a><a name="getdlghost"></a>CWindow::GetDlgHost  
 Извлекает указатель на интерфейс для управления ATL, размещение контейнера.  
  
```
HRESULT GetDlgHost(  
    int nID,
    REFIID iid,
    void** ppHost) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 [in] Идентификатор ресурса, извлекаемого элемента управления.  
  
 `iid`  
 [in] Идентификатор интерфейса, который вы хотите получить от элемента управления.  
  
 *ppHost*  
 [out] Указатель на интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` Если заданные окна `iid` — это контейнер элемента управления и может получить запрошенный интерфейс. Возвращает **E_FAIL** Если окно не является контейнер элемента управления, или не удалось получить запрошенный интерфейс. Если окна с указанным Идентификатором не найден, то возвращаемое значение равно HRESULT_FROM_WIN32(ERROR_CONTROL_ID_NOT_FOUND).  
  
### <a name="remarks"></a>Примечания  
 Этот указатель можно вызывать методы интерфейса.  
  
##  <a name="a-namegetdlgitema--cwindowgetdlgitem"></a><a name="getdlgitem"></a>CWindow::GetDlgItem  
 Возвращает указанное дочернее окно.  
  
```
HWND GetDlgItem(int nID) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetDlgItem](http://msdn.microsoft.com/library/windows/desktop/ms645481) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdlgiteminta--cwindowgetdlgitemint"></a><a name="getdlgitemint"></a>CWindow::GetDlgItemInt  
 Преобразует текст элемента управления в целое число.  
  
```
UINT GetDlgItemInt(  
    int nID,
    BOOL* lpTrans = NULL,
    BOOL bSigned = TRUE) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetDlgItemInt](http://msdn.microsoft.com/library/windows/desktop/ms645485) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdlgitemtexta--cwindowgetdlgitemtext"></a><a name="getdlgitemtext"></a>CWindow::GetDlgItemText  
 Извлекает текст элемента управления.  
  
```
UINT GetDlgItemText(  
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const throw();

BOOL GetDlgItemText(  
    int nID,
    BSTR& bstrText) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetDlgItemText](http://msdn.microsoft.com/library/windows/desktop/ms645489) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Вторая версия этого метода позволяет копировать текст элемента управления `BSTR`. Данная версия возвращает **TRUE** Если текст, скопированный успешно, в противном случае, **FALSE**.  
  
##  <a name="a-namegetexstylea--cwindowgetexstyle"></a><a name="getexstyle"></a>CWindow::GetExStyle  
 Извлекает расширенные стили окна окна.  
  
```
DWORD GetExStyle() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окно расширенных стилей.  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить стили регулярных окна, вызовите [GetStyle](#getstyle).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#10;](../../atl/codesnippet/cpp/cwindow-class_10.cpp)]  
  
##  <a name="a-namegetfonta--cwindowgetfont"></a><a name="getfont"></a>CWindow::GetFont  
 Извлекает текущий шрифт окна путем отправки [WM_GETFONT](http://msdn.microsoft.com/library/windows/desktop/ms632624) сообщения в окне.  
  
```
HFONT GetFont() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор шрифта.  
  
##  <a name="a-namegethotkeya--cwindowgethotkey"></a><a name="gethotkey"></a>CWindow::GetHotKey  
 Определяет сочетания клавиш, связанные с окном, отправляя **WM_GETHOTKEY** сообщений.  
  
```
DWORD GetHotKey() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Виртуальный код клавиши и модификаторов для сочетания клавиш, связанных с этим окном. Список возможных модификаторы см [WM_GETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646278) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Список стандартных кодов виртуального ключа см. в разделе Winuser.h.  
  
##  <a name="a-namegeticona--cwindowgeticon"></a><a name="geticon"></a>CWindow::GetIcon  
 Получает дескриптор окна крупных или мелких значков.  
  
```
HICON GetIcon(BOOL bBigIcon = TRUE) const;
```  
  
### <a name="parameters"></a>Параметры  
 `bBigIcon`  
 [in] Если **TRUE** (значение по умолчанию), метод возвращает крупных значков. В противном случае — возвращает мелкого значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка.  
  
### <a name="remarks"></a>Примечания  
 `GetIcon`отправляет [WM_GETICON](http://msdn.microsoft.com/library/windows/desktop/ms632625) сообщения в окне.  
  
##  <a name="a-namegetlastactivepopupa--cwindowgetlastactivepopup"></a><a name="getlastactivepopup"></a>CWindow::GetLastActivePopup  
 Возвращает последнюю активную всплывающего окна.  
  
```
HWND GetLastActivePopup() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetLastActivePopup](http://msdn.microsoft.com/library/windows/desktop/ms633507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmenua--cwindowgetmenu"></a><a name="getmenu"></a>CWindow::GetMenu  
 Извлекает меню окна.  
  
```
HMENU GetMenu() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetMenu](http://msdn.microsoft.com/library/windows/desktop/ms647640) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetnextdlggroupitema--cwindowgetnextdlggroupitem"></a><a name="getnextdlggroupitem"></a>CWindow::GetNextDlgGroupItem  
 Возвращает предыдущий или следующий элемент управления в группе элементов управления.  
  
```
HWND GetNextDlgGroupItem(HWND hWndCtl, BOOL bPrevious = FALSE) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetNextDlgGroupItem](http://msdn.microsoft.com/library/windows/desktop/ms645492) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetnextdlgtabitema--cwindowgetnextdlgtabitem"></a><a name="getnextdlgtabitem"></a>CWindow::GetNextDlgTabItem  
 Извлекает наличие предыдущего или следующего элемента управления **WS_TABSTOP** стиль.  
  
```
HWND GetNextDlgTabItem(HWND hWndCtl, BOOL bPrevious = FALSE) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetNextDlgTabItem](http://msdn.microsoft.com/library/windows/desktop/ms645495) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetparenta--cwindowgetparent"></a><a name="getparent"></a>CWindow::GetParent  
 Получает непосредственный родительский окна.  
  
```
HWND GetParent() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetParent](http://msdn.microsoft.com/library/windows/desktop/ms633510) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&11;](../../atl/codesnippet/cpp/cwindow-class_11.cpp)]  
  
##  <a name="a-namegetscrollinfoa--cwindowgetscrollinfo"></a><a name="getscrollinfo"></a>CWindow::GetScrollInfo  
 Извлекает параметры полосы прокрутки.  
  
```
BOOL GetScrollInfo(int nBar, LPSCROLLINFO lpScrollInfo) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetScrollInfo](http://msdn.microsoft.com/library/windows/desktop/bb787583) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetscrollposa--cwindowgetscrollpos"></a><a name="getscrollpos"></a>CWindow::GetScrollPos  
 Получает положение ползунка полосы прокрутки.  
  
```
int GetScrollPos(int nBar) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetscrollrangea--cwindowgetscrollrange"></a><a name="getscrollrange"></a>CWindow::GetScrollRange  
 Возвращает диапазон значений для полосы прокрутки.  
  
```
BOOL GetScrollRange(  
    int nBar,
    LPINT lpMinPos,
    LPINT lpMaxPos) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetScrollRange](http://msdn.microsoft.com/library/windows/desktop/bb787587) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstylea--cwindowgetstyle"></a><a name="getstyle"></a>CWindow::GetStyle  
 Получает стили окна, окна.  
  
```
DWORD GetStyle() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стили окна.  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить расширенные стили окна, вызовите [GetExStyle](#getexstyle).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#12;](../../atl/codesnippet/cpp/cwindow-class_12.cpp)]  
  
##  <a name="a-namegetsystemmenua--cwindowgetsystemmenu"></a><a name="getsystemmenu"></a>CWindow::GetSystemMenu  
 Создает копию объекта меню системы для изменения.  
  
```
HMENU GetSystemMenu(BOOL bRevert) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetSystemMenu](http://msdn.microsoft.com/library/windows/desktop/ms647985) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettoplevelparenta--cwindowgettoplevelparent"></a><a name="gettoplevelparent"></a>CWindow::GetTopLevelParent  
 Получает окно верхнего уровня родительского окна.  
  
```
HWND GetTopLevelParent() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна верхнего уровня родительского.  
  
##  <a name="a-namegettoplevelwindowa--cwindowgettoplevelwindow"></a><a name="gettoplevelwindow"></a>CWindow::GetTopLevelWindow  
 Получает окно верхнего уровня владельцу или родительского окна.  
  
```
HWND GetTopLevelWindow() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна-владельца верхнего уровня.  
  
##  <a name="a-namegettopwindowa--cwindowgettopwindow"></a><a name="gettopwindow"></a>CWindow::GetTopWindow  
 Возвращает дочернее окно верхнего уровня.  
  
```
HWND GetTopWindow() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetTopWindow](http://msdn.microsoft.com/library/windows/desktop/ms633514) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#13;](../../atl/codesnippet/cpp/cwindow-class_13.cpp)]  
  
##  <a name="a-namegetupdaterecta--cwindowgetupdaterect"></a><a name="getupdaterect"></a>CWindow::GetUpdateRect  
 Возвращает координаты наименьший прямоугольник, ограничивающий область обновления полностью.  
  
```
BOOL GetUpdateRect(LPRECT lpRect, BOOL bErase = FALSE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetUpdateRect](http://msdn.microsoft.com/library/windows/desktop/dd144943) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetupdatergna--cwindowgetupdatergn"></a><a name="getupdatergn"></a>CWindow::GetUpdateRgn  
 Получает область обновления и копирует их в заданной области.  
  
```
int GetUpdateRgn(HRGN hRgn, BOOL bErase = FALSE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetUpdateRgn](http://msdn.microsoft.com/library/windows/desktop/dd144944) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowa--cwindowgetwindow"></a><a name="getwindow"></a>CWindow::GetWindow  
 Извлекает заданное окно.  
  
```
HWND GetWindow(UINT nCmd) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 See `GetWindow` in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowcontexthelpida--cwindowgetwindowcontexthelpid"></a><a name="getwindowcontexthelpid"></a>CWindow::GetWindowContextHelpId  
 Получает идентификатор контекста справки окна.  
  
```
DWORD GetWindowContextHelpId() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowContextHelpId](http://msdn.microsoft.com/library/windows/desktop/bb776429) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowdca--cwindowgetwindowdc"></a><a name="getwindowdc"></a>CWindow::GetWindowDC  
 Получает контекст устройства для всего содержимого окна.  
  
```
HDC GetWindowDC() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#14;](../../atl/codesnippet/cpp/cwindow-class_14.cpp)]  
  
##  <a name="a-namegetwindowlonga--cwindowgetwindowlong"></a><a name="getwindowlong"></a>CWindow::GetWindowLong  
 Получает 32-разрядное значение с указанным смещением в открытое окно память.  
  
```
LONG GetWindowLong(int nIndex) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Чтобы написать код, который совместим с 32-разрядной и 64-разрядных версиях Windows, используйте [CWindow::GetWindowLongPtr](#getwindowlongptr).  
  
##  <a name="a-namegetwindowlongptra--cwindowgetwindowlongptr"></a><a name="getwindowlongptr"></a>CWindow::GetWindowLongPtr  
 Извлекает сведения о указанного окна, включая значение с указанным смещением в открытое окно память.  
  
```
LONG_PTR GetWindowLongPtr(int nIndex) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowLongPtr](http://msdn.microsoft.com/library/windows/desktop/ms633585) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить указатель или дескриптор, эта функция замещает `CWindow::GetWindowLong` метод.  
  
> [!NOTE]
>  Указатели и дескрипторы являются 32 бита в 32-разрядной Windows и 64 бита в 64-разрядной версии Windows.  
  
 Чтобы написать код, который совместим с 32-разрядной и 64-разрядных версиях Windows, используйте `CWindow::GetWindowLongPtr`.  
  
##  <a name="a-namegetwindowplacementa--cwindowgetwindowplacement"></a><a name="getwindowplacement"></a>CWindow::GetWindowPlacement  
 Извлекает show state и позиций.  
  
```
BOOL GetWindowPlacement(WINDOWPLACEMENT FAR* lpwndpl) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowPlacement](http://msdn.microsoft.com/library/windows/desktop/ms633518) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowprocessida--cwindowgetwindowprocessid"></a><a name="getwindowprocessid"></a>CWindow::GetWindowProcessID  
 Извлекает идентификатор процесса, который окно создал.  
  
```
DWORD GetWindowProcessID() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowThreadProcessID](http://msdn.microsoft.com/library/windows/desktop/ms633522) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#15;](../../atl/codesnippet/cpp/cwindow-class_15.cpp)]  
  
##  <a name="a-namegetwindowrecta--cwindowgetwindowrect"></a><a name="getwindowrect"></a>CWindow::GetWindowRect  
 Возвращает ограничивающий размеры окна.  
  
```
BOOL GetWindowRect(LPRECT lpRect) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowRect](http://msdn.microsoft.com/library/windows/desktop/ms633519) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowrgna--cwindowgetwindowrgn"></a><a name="getwindowrgn"></a>CWindow::GetWindowRgn  
 Получает копию этой области окна.  
  
```
int GetWindowRgn(HRGN hRgn) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowRgn](http://msdn.microsoft.com/library/windows/desktop/dd144950) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowtexta--cwindowgetwindowtext"></a><a name="getwindowtext"></a>CWindow::GetWindowText  
 Извлекает текст окна.  
  
```
int GetWindowText(LPTSTR lpszStringBuf, int nMaxCount) const throw();
BOOL GetWindowText(BSTR& bstrText) throw();
int GetWindowText(CSimpleString& strText) const;
```  
  
### <a name="parameters"></a>Параметры  
 `lpszStringBuf`  
 Буфер, в который записывается текст окна.  
  
 `nMaxCount`  
 Размер буфера в символах; соответствует также максимальному числу символов для записи.  
  
 `bstrText`  
 Объект `BSTR` для хранения текста окна.  
  
 `strText`  
 Объект `CString` для хранения текста окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если текст успешно скопированы, возвращаемое значение равно **TRUE**; в противном случае, возвращается значение **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowText](http://msdn.microsoft.com/library/windows/desktop/ms633520) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Вторая версия этого метода позволяет сохранять текст в `BSTR`; третья версия позволяет хранить результаты в [CString](../../atl-mfc-shared/reference/cstringt-class.md), поскольку `CSimpleString` является базовым классом для `CString`.  
  
##  <a name="a-namegetwindowtextlengtha--cwindowgetwindowtextlength"></a><a name="getwindowtextlength"></a>CWindow::GetWindowTextLength  
 Получает длину текстового окна.  
  
```
int GetWindowTextLength() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowTextLength](http://msdn.microsoft.com/library/windows/desktop/ms633521) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowthreadida--cwindowgetwindowthreadid"></a><a name="getwindowthreadid"></a>CWindow::GetWindowThreadID  
 Получает идентификатор потока, который создал указанного окна.  
  
```
DWORD GetWindowThreadID() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowThreadProcessID](http://msdn.microsoft.com/library/windows/desktop/ms633522) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing №&16;](../../atl/codesnippet/cpp/cwindow-class_16.cpp)]  
  
##  <a name="a-namegetwindowworda--cwindowgetwindowword"></a><a name="getwindowword"></a>CWindow::GetWindowWord  
 Возвращает 16-разрядное значение с указанным смещением в открытое окно память.  
  
```
WORD GetWindowWord(int nIndex) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegotodlgctrla--cwindowgotodlgctrl"></a><a name="gotodlgctrl"></a>CWindow::GotoDlgCtrl  
 Устанавливает фокус на элемент управления в диалоговом окне.  
  
```
void GotoDlgCtrl(HWND hWndCtrl) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [WM_NEXTDLGCTL](http://msdn.microsoft.com/library/windows/desktop/ms645432) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehidecareta--cwindowhidecaret"></a><a name="hidecaret"></a>CWindow::HideCaret  
 Скрывает курсор системы.  
  
```
BOOL HideCaret() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [HideCaret](http://msdn.microsoft.com/library/windows/desktop/ms648403) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&17;](../../atl/codesnippet/cpp/cwindow-class_17.cpp)]  
  
##  <a name="a-namehilitemenuitema--cwindowhilitemenuitem"></a><a name="hilitemenuitem"></a>CWindow::HiliteMenuItem  
 Выделяет или снимает выделение с меню верхнего уровня.  
  
```
BOOL HiliteMenuItem(  
    HMENU hMenu,
    UINT uHiliteItem,
    UINT uHilite) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [HiliteMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647986) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinvalidatea--cwindowinvalidate"></a><a name="invalidate"></a>CWindow::Invalidate  
 Делает недействительной всю клиентскую область.  
  
```
BOOL Invalidate(BOOL bErase = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [InvalidateRect](http://msdn.microsoft.com/library/windows/desktop/dd145002) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Передает **NULL** для `RECT` параметр `InvalidateRect` функции Win32.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&18;](../../atl/codesnippet/cpp/cwindow-class_18.cpp)]  
  
##  <a name="a-nameinvalidaterecta--cwindowinvalidaterect"></a><a name="invalidaterect"></a>CWindow::InvalidateRect  
 Делает недействительной клиентской области в заданном прямоугольнике.  
  
```
BOOL InvalidateRect(LPCRECT lpRect, BOOL bErase = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [InvalidateRect](http://msdn.microsoft.com/library/windows/desktop/dd145002) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinvalidatergna--cwindowinvalidatergn"></a><a name="invalidatergn"></a>CWindow::InvalidateRgn  
 Делает недействительной клиентской области в пределах указанной области.  
  
```
void InvalidateRgn(HRGN hRgn, BOOL bErase = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [InvalidateRgn](http://msdn.microsoft.com/library/windows/desktop/dd145003) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Указывает `void` типа возвращаемого значения, а `InvalidateRgn` Win32 функция всегда возвращает **TRUE**.  
  
##  <a name="a-nameischilda--cwindowischild"></a><a name="ischild"></a>CWindow::IsChild  
 Определяет, является ли заданное окно дочернего окна.  
  
```
BOOL IsChild(const HWND hWnd) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsChild](http://msdn.microsoft.com/library/windows/desktop/ms633524) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisdialogmessagea--cwindowisdialogmessage"></a><a name="isdialogmessage"></a>CWindow::IsDialogMessage  
 Определяет, является ли сообщение предназначено для указанного диалогового.  
  
```
BOOL IsDialogMessage(LPMSG lpMsg) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsDialogMessage](http://msdn.microsoft.com/library/windows/desktop/ms645498) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisdlgbuttoncheckeda--cwindowisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>CWindow::IsDlgButtonChecked  
 Определяет состояние флажка кнопки.  
  
```
UINT IsDlgButtonChecked(int nIDButton) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsDlgButtonChecked](http://msdn.microsoft.com/library/windows/desktop/bb761879) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisiconica--cwindowisiconic"></a><a name="isiconic"></a>CWindow::IsIconic  
 Определяет, свернута ли окно.  
  
```
BOOL IsIconic() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsIconic](http://msdn.microsoft.com/library/windows/desktop/ms633527) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&19;](../../atl/codesnippet/cpp/cwindow-class_19.cpp)]  
  
##  <a name="a-nameisparentdialoga--cwindowisparentdialog"></a><a name="isparentdialog"></a>CWindow::IsParentDialog  
 Определяет, является ли родительского окна элемента управления, появится диалоговое окно.  
  
```
BOOL IsParentDialog() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE если родительское окно диалога, значение FALSE в противном случае.  
  
##  <a name="a-nameiswindowa--cwindowiswindow"></a><a name="iswindow"></a>CWindow::IsWindow  
 Определяет, является ли заданный дескриптор окна определяет существующее окно.  
  
```
BOOL IsWindow() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsWindow](http://msdn.microsoft.com/library/windows/desktop/ms633528) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&20;](../../atl/codesnippet/cpp/cwindow-class_20.cpp)]  
  
##  <a name="a-nameiswindowenableda--cwindowiswindowenabled"></a><a name="iswindowenabled"></a>CWindow::IsWindowEnabled  
 Определяет, включен ли окно для ввода данных.  
  
```
BOOL IsWindowEnabled() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsWindowEnabled](http://msdn.microsoft.com/library/windows/desktop/ms646303) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#21;](../../atl/codesnippet/cpp/cwindow-class_21.cpp)]  
  
##  <a name="a-nameiswindowvisiblea--cwindowiswindowvisible"></a><a name="iswindowvisible"></a>CWindow::IsWindowVisible  
 Определяет состояние видимость окна.  
  
```
BOOL IsWindowVisible() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsWindowVisible](http://msdn.microsoft.com/library/windows/desktop/ms633530) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#22;](../../atl/codesnippet/cpp/cwindow-class_22.cpp)]  
  
##  <a name="a-nameiswindowunicodea--cwindowiswindowunicode"></a><a name="iswindowunicode"></a>CWindow::IsWindowUnicode  
 Определяет, является ли заданное окно собственного окна Юникода.  
  
```
BOOL IsWindowUnicode() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsWindowUnicode](http://msdn.microsoft.com/library/windows/desktop/ms633529) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#23;](../../atl/codesnippet/cpp/cwindow-class_23.cpp)]  
  
##  <a name="a-nameiszoomeda--cwindowiszoomed"></a><a name="iszoomed"></a>CWindow::IsZoomed  
 Определяет, является ли окно развернуто.  
  
```
BOOL IsZoomed() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IsZoomed](http://msdn.microsoft.com/library/windows/desktop/ms633531) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namekilltimera--cwindowkilltimer"></a><a name="killtimer"></a>CWindow::KillTimer  
 Удаляет событие таймера, созданных `CWindow::SetTimer`.  
  
```
BOOL KillTimer(UINT nIDEvent) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [KillTimer](http://msdn.microsoft.com/library/windows/desktop/ms644903) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namelockwindowupdatea--cwindowlockwindowupdate"></a><a name="lockwindowupdate"></a>CWindow::LockWindowUpdate  
 Отключает или включает рисования в окне путем вызова [LockWindowUpdate](http://msdn.microsoft.com/library/windows/desktop/dd145034) функции Win32.  
  
```
BOOL LockWindowUpdate(BOOL bLock = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bLock`  
 [in] Если **TRUE** (значение по умолчанию), окно будет заблокировано. В противном случае она будет разблокирована.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если окно успешно заблокирован; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если `bLock` — **TRUE**, этот метод передает [m_hWnd](#m_hwnd) функции Win32; в противном случае, он передает **NULL**.  
  
##  <a name="a-namemhwnda--cwindowmhwnd"></a><a name="m_hwnd"></a>CWindow::m_hWnd  
 Содержит дескриптор окна, связанный с `CWindow` объекта.  
  
```
HWND m_hWnd throw() throw();
```  
  
##  <a name="a-namemapwindowpointsa--cwindowmapwindowpoints"></a><a name="mapwindowpoints"></a>CWindow::MapWindowPoints  
 Преобразует набор точек из координат окна пространства координат в другом окне.  
  
```
int MapWindowPoints(  
    HWND hWndTo,
    LPPOINT lpPoint,
    UINT nCount) const throw();

int MapWindowPoints(  
    HWND hWndTo,
    LPRECT lpRect) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [MapWindowPoints](http://msdn.microsoft.com/library/windows/desktop/dd145046) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Вторая версия этого метода позволяет преобразовать координаты [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
##  <a name="a-namemessageboxa--cwindowmessagebox"></a><a name="messagebox"></a>CWindow::MessageBox  
 Отображает окно сообщения.  
  
```
int MessageBox(  
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = NULL,
    UINT nType = MB_OK) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#24;](../../atl/codesnippet/cpp/cwindow-class_24.cpp)]  
  
##  <a name="a-namemodifystylea--cwindowmodifystyle"></a><a name="modifystyle"></a>CWindow::ModifyStyle  
 Изменение стилей окна `CWindow` объекта.  
  
```
BOOL ModifyStyle(  
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwRemove`  
 [in] Задает стили окна удаляется при изменении стиля.  
  
 `dwAdd`  
 [in] Задает стили окна для добавления при изменении стиля.  
  
 `nFlags`  
 [in] Флаги размещения окна. Список возможных значений см. в разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если стили окна изменен; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Стили, чтобы добавить или удалить можно комбинировать с помощью побитового или (|) оператор. В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]сведения о стилях доступных окон.  
  
 Если `nFlags` не равно нулю, `ModifyStyle` вызывает функцию Win32 `SetWindowPos`и перерисовывает окно путем объединения `nFlags` с использованием следующих четырех флагов:  
  
- `SWP_NOSIZE`Сохраняет текущий размер.  
  
- `SWP_NOMOVE`Сохраняет текущую позицию.  
  
- `SWP_NOZORDER`Сохраняет текущий Z-порядка.  
  
- `SWP_NOACTIVATE`Не активируйте окно.  
  
 Изменение в окне расширенных стилей, вызовите метод [ModifyStyleEx](#modifystyleex).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#25;](../../atl/codesnippet/cpp/cwindow-class_25.cpp)]  
  
##  <a name="a-namemodifystyleexa--cwindowmodifystyleex"></a><a name="modifystyleex"></a>CWindow::ModifyStyleEx  
 Изменяет расширенные стили окна из `CWindow` объекта.  
  
```
BOOL ModifyStyleEx(  
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwRemove`  
 [in] Задает расширенные стили удаляется при изменении стиля.  
  
 `dwAdd`  
 [in] Задает расширенные стили для добавления при изменении стиля.  
  
 `nFlags`  
 [in] Флаги размещения окна. Список возможных значений см. в разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если расширенные стили окна изменен; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Стили, чтобы добавить или удалить можно комбинировать с помощью побитового или (|) оператор. В разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]сведения о доступных расширенные стили.  
  
 Если `nFlags` не равно нулю, `ModifyStyleEx` вызывает функцию Win32 `SetWindowPos`и перерисовывает окно путем объединения `nFlags` с использованием следующих четырех флагов:  
  
- `SWP_NOSIZE`Сохраняет текущий размер.  
  
- `SWP_NOMOVE`Сохраняет текущую позицию.  
  
- `SWP_NOZORDER`Сохраняет текущий Z-порядка.  
  
- `SWP_NOACTIVATE`Не активируйте окно.  
  
 Чтобы изменить стили регулярных окна с помощью windows, вызовите [ModifyStyle](#modifystyle).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#26;](../../atl/codesnippet/cpp/cwindow-class_26.cpp)]  
  
##  <a name="a-namemovewindowa--cwindowmovewindow"></a><a name="movewindow"></a>CWindow::MoveWindow  
 Изменяет размер и положение окна.  
  
```
BOOL MoveWindow(  
    int x,
    int y,
    int nWidth,
    int nHeight,
    BOOL bRepaint = TRUE) throw();

BOOL MoveWindow(  
    LPCRECT lpRect,
    BOOL bRepaint = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Для окна верхнего уровня параметры объекта, x и y являются относительно верхнего левого угла экрана. Для дочернего объекта окна они являются относительно левого верхнего угла клиентской области родительского окна.  
  
 Вторая версия этого метода использует [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, чтобы определить новое положение, ширину и высоту окна.  
  
##  <a name="a-namenextdlgctrla--cwindownextdlgctrl"></a><a name="nextdlgctrl"></a>CWindow::NextDlgCtrl  
 Устанавливает фокус на следующий элемент управления в диалоговом окне.  
  
```
void NextDlgCtrl() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [WM_NEXTDLGCTL](http://msdn.microsoft.com/library/windows/desktop/ms645432) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameopenclipboarda--cwindowopenclipboard"></a><a name="openclipboard"></a>CWindow::OpenClipboard  
 Открывает буфер обмена.  
  
```
BOOL OpenClipboard() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameoperatorhwnda--cwindowoperator-hwnd"></a><a name="operator_hwnd"></a>CWindow::operator HWND  
 Преобразует `CWindow` объект `HWND`.  
  
```  
operator HWND() const throw();
```  
  
##  <a name="a-nameoperatoreqa--cwindowoperator-"></a><a name="operator_eq"></a>CWindow::operator =  
 Назначает `HWND` для `CWindow` объектом, присвоив [m_hWnd](#m_hwnd) члена `hWnd`.  
  
```
CWindow& operator= (HWND hWnd) throw();
```  
  
##  <a name="a-namepostmessagea--cwindowpostmessage"></a><a name="postmessage"></a>CWindow::PostMessage  
 Помещает сообщение в очередь сообщений, связанных с потоком, создавший окно.  
  
```
BOOL PostMessage(  
    UINT message,
    WPARAM wParam = 0,
    LPARAM lParam = 0) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [PostMessage](http://msdn.microsoft.com/library/windows/desktop/ms644944) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Возвращает значение, не ждет поток для обработки сообщения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#27;](../../atl/codesnippet/cpp/cwindow-class_27.cpp)]  
  
##  <a name="a-nameprevdlgctrla--cwindowprevdlgctrl"></a><a name="prevdlgctrl"></a>CWindow::PrevDlgCtrl  
 Устанавливает фокус на предыдущий элемент управления в диалоговом окне.  
  
```
void PrevDlgCtrl() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [WM_NEXTDLGCTL](http://msdn.microsoft.com/library/windows/desktop/ms645432) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameprinta--cwindowprint"></a><a name="print"></a>CWindow::Print  
 Отправляет [WM_PRINT](http://msdn.microsoft.com/library/windows/desktop/dd145216) сообщение в окно запроса, что он себя нарисовать в заданном контексте устройства.  
  
```
void Print(HDC hDC, DWORD dwFlags) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hDC`  
 [in] Дескриптор контекста устройства.  
  
 `dwFlags`  
 [in] Указывает параметры отрисовки. Можно объединить один или несколько из следующих флагов:  
  
- `PRF_CHECKVISIBLE`Нарисуйте окна только в том случае, если она отображается.  
  
- `PRF_CHILDREN`Рисование всех видимых дочерних окон.  
  
- `PRF_CLIENT`Нарисуйте клиентской области окна.  
  
- `PRF_ERASEBKGND`Стереть фон перед рисованием окна.  
  
- `PRF_NONCLIENT`Нарисуйте неклиентской области окна.  
  
- `PRF_OWNED`Нарисуйте все собственные окна.  
  
##  <a name="a-nameprintclienta--cwindowprintclient"></a><a name="printclient"></a>CWindow::PrintClient  
 Отправляет [WM_PRINTCLIENT](http://msdn.microsoft.com/library/windows/desktop/dd145217) сообщение в окно запроса, что его нарисовать клиентской области в заданном контексте устройства.  
  
```
void PrintClient(HDC hDC, DWORD dwFlags) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hDC`  
 [in] Дескриптор контекста устройства.  
  
 `dwFlags`  
 [in] Указывает параметры отрисовки. Можно объединить один или несколько из следующих флагов:  
  
- `PRF_CHECKVISIBLE`Нарисуйте окна только в том случае, если она отображается.  
  
- `PRF_CHILDREN`Рисование всех видимых дочерних окон.  
  
- `PRF_CLIENT`Нарисуйте клиентской области окна.  
  
- `PRF_ERASEBKGND`Стереть фон перед рисованием окна.  
  
- `PRF_NONCLIENT`Нарисуйте неклиентской области окна.  
  
- `PRF_OWNED`Нарисуйте все собственные окна.  
  
##  <a name="a-namercdefaulta--cwindowrcdefault"></a><a name="rcdefault"></a>CWindow::rcDefault  
 Содержит размеры окна по умолчанию.  
  
```
static RECT rcDefault;
```  
  
##  <a name="a-nameredrawwindowa--cwindowredrawwindow"></a><a name="redrawwindow"></a>CWindow::RedrawWindow  
 Обновляет указанный прямоугольник или область в клиентской области.  
  
```
BOOL RedrawWindow(  
    LPCRECT lpRectUpdate = NULL,
    HRGN hRgnUpdate = NULL,
    UINT flags = RDW_INVALIDATE | RDW_UPDATENOW | RDW_ERASE);

throw()
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#28;](../../atl/codesnippet/cpp/cwindow-class_28.cpp)]  
  
##  <a name="a-namereleasedca--cwindowreleasedc"></a><a name="releasedc"></a>CWindow::ReleaseDC  
 Освобождает контекст устройства.  
  
```
int ReleaseDC(HDC hDC);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing №&9;](../../atl/codesnippet/cpp/cwindow-class_9.cpp)]  
  
##  <a name="a-nameresizeclienta--cwindowresizeclient"></a><a name="resizeclient"></a>CWindow::ResizeClient  
 Изменяет размер окна до размера указанной клиентской области.  
  
```
BOOL ResizeClient(  
    int nWidth,
    int nHeight,
    BOOL bRedraw = FALSE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Новая ширина окна в пикселях.  
  
 `nHeight`  
 Новая высота окна в пикселях.  
  
 `bRedraw`  
 Флаг, указывающий необходимость перерисовки изменения. Значение по умолчанию — **FALSE**, окно, показывающее не будут перерисовываться изменения.  
  
##  <a name="a-namescreentoclienta--cwindowscreentoclient"></a><a name="screentoclient"></a>CWindow::ScreenToClient  
 Преобразует координат экрана в клиентских координатах.  
  
```
BOOL ScreenToClient(LPPOINT lpPoint) const throw();
BOOL ScreenToClient(LPRECT lpRect) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ScreenToClient](http://msdn.microsoft.com/library/windows/desktop/dd162952) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Вторая версия этого метода позволяет преобразовать координаты [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
##  <a name="a-namescrollwindowa--cwindowscrollwindow"></a><a name="scrollwindow"></a>CWindow::ScrollWindow  
 Прокручивает указанной клиентской области.  
  
```
BOOL ScrollWindow(  
    int xAmount,
    int yAmount,
    LPCRECT lpRect = NULL,
    LPCRECT lpClipRect = NULL) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ScrollWindow](http://msdn.microsoft.com/library/windows/desktop/bb787591) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namescrollwindowexa--cwindowscrollwindowex"></a><a name="scrollwindowex"></a>CWindow::ScrollWindowEx  
 Прокручивает указанной клиентской области с дополнительными возможностями.  
  
```
int ScrollWindowEx(  
    int dx,
    int dy,
    LPCRECT lpRectScroll,
    LPCRECT lpRectClip,
    HRGN hRgnUpdate,
    LPRECT lpRectUpdate,
    UINT flags) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ScrollWindowEx](http://msdn.microsoft.com/library/windows/desktop/bb787593) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesenddlgitemmessagea--cwindowsenddlgitemmessage"></a><a name="senddlgitemmessage"></a>CWindow::SendDlgItemMessage  
 Отправляет сообщение в элемент управления.  
  
```
LRESULT SendDlgItemMessage(  
    int nID,
    UINT message,
    WPARAM wParam = 0,
    LPARAM lParam = 0) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SendDlgItemMessage](http://msdn.microsoft.com/library/windows/desktop/ms645515) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesendmessagea--cwindowsendmessage"></a><a name="sendmessage"></a>CWindow::SendMessage  
 Отправляет сообщение в окно и не возвращается, пока не обработал сообщение процедуре окна.  
  
```
LRESULT SendMessage(  
    UINT message,
    WPARAM wParam = 0,
    LPARAM lParam = 0) throw();

static LRESULT SendMessage(  
    HWND hWnd,
    UINT message,
    WPARAM wParam,
    LPARAM lParam) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#29;](../../atl/codesnippet/cpp/cwindow-class_29.cpp)]  
  
##  <a name="a-namesendmessagetodescendantsa--cwindowsendmessagetodescendants"></a><a name="sendmessagetodescendants"></a>CWindow::SendMessageToDescendants  
 Отправляет указанное сообщение все непосредственные потомки `CWindow` объекта.  
  
```
void SendMessageToDescendants(  
    UINT message,
    WPARAM wParam = 0,
    LPARAM lParam = 0,
    BOOL bDeep = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `message`  
 [in] Отправляемое сообщение.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `bDeep`  
 [in] Если **TRUE** (значение по умолчанию), это сообщение будет отправлено на всех потомков windows; в противном случае — он будет отправляться только непосредственные дочерние windows.  
  
### <a name="remarks"></a>Примечания  
 Если `bDeep` — **TRUE**, кроме того отправляется на все дочерние окна.  
  
##  <a name="a-namesendnotifymessagea--cwindowsendnotifymessage"></a><a name="sendnotifymessage"></a>CWindow::SendNotifyMessage  
 Отправляет сообщение в окно.  
  
```
BOOL SendNotifyMessage(  
    UINT message,
    WPARAM wParam = 0,
    LPARAM lParam = 0) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SendNotifyMessage](http://msdn.microsoft.com/library/windows/desktop/ms644953) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если окно было создано вызывающим потоком `SendNotifyMessage` не возвращается, пока не обработал сообщение процедуре окна. В противном случае возвращается немедленно.  
  
##  <a name="a-namesetactivewindowa--cwindowsetactivewindow"></a><a name="setactivewindow"></a>CWindow::SetActiveWindow  
 Активирует окно.  
  
```
HWND SetActiveWindow() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646311) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#30;](../../atl/codesnippet/cpp/cwindow-class_30.cpp)]  
  
##  <a name="a-namesetcapturea--cwindowsetcapture"></a><a name="setcapture"></a>CWindow::SetCapture  
 Отправляет все последующие мыши в окне.  
  
```
HWND SetCapture() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetCapture](http://msdn.microsoft.com/library/windows/desktop/ms646262) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetclipboardviewera--cwindowsetclipboardviewer"></a><a name="setclipboardviewer"></a>CWindow::SetClipboardViewer  
 Добавляет окно в цепочку просмотра буфера обмена.  
  
```
HWND SetClipboardViewer() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetClipboardViewer](http://msdn.microsoft.com/library/windows/desktop/ms649052) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetdlgctrlida--cwindowsetdlgctrlid"></a><a name="setdlgctrlid"></a>CWindow::SetDlgCtrlID  
 Задает идентификатор окна с указанным значением.  
  
```
int SetDlgCtrlID(int nID) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 [in] Новое значение для идентификатора окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения предыдущих идентификатор окна. в противном случае — 0.  
  
##  <a name="a-namesetdlgiteminta--cwindowsetdlgitemint"></a><a name="setdlgitemint"></a>CWindow::SetDlgItemInt  
 Изменяет текст элемента управления в строковое представление целого числа.  
  
```
BOOL SetDlgItemInt(  
    int nID,
    UINT nValue,
    BOOL bSigned = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetDlgItemInt](http://msdn.microsoft.com/library/windows/desktop/ms645518) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetdlgitemtexta--cwindowsetdlgitemtext"></a><a name="setdlgitemtext"></a>CWindow::SetDlgItemText  
 Изменение текста элемента управления.  
  
```
BOOL SetDlgItemText(int nID, LPCTSTR lpszString) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetDlgItemText](http://msdn.microsoft.com/library/windows/desktop/ms645521) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetfocusa--cwindowsetfocus"></a><a name="setfocus"></a>CWindow::SetFocus  
 Устанавливает фокус ввода в окно.  
  
```
HWND SetFocus() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#31;](../../atl/codesnippet/cpp/cwindow-class_31.cpp)]  
  
##  <a name="a-namesetfonta--cwindowsetfont"></a><a name="setfont"></a>CWindow::SetFont  
 Изменяет текущий шрифт окна путем отправки [WM_SETFONT](http://msdn.microsoft.com/library/windows/desktop/ms632642) сообщения в окне.  
  
```
void SetFont(HFONT hFont, BOOL bRedraw = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hFont`  
 [in] Дескриптор для нового шрифта.  
  
 `bRedraw`  
 [in] Если **TRUE** (значение по умолчанию), окно перерисовывается. В противном случае — не является.  
  
##  <a name="a-namesethotkeya--cwindowsethotkey"></a><a name="sethotkey"></a>CWindow::SetHotKey  
 Связывает сочетания клавиш с окном, отправляя **WM_SETHOTKEY** сообщений.  
  
```
int SetHotKey(WORD wVirtualKeyCode, WORD wModifiers) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `wVirtualKeyCode`  
 [in] Виртуальный код сочетания клавиш. Список стандартных кодов виртуального ключа см. в разделе Winuser.h.  
  
 `wModifiers`  
 [in] Модификаторы клавиш. Список возможных значений см. в разделе **WM_SETHOTKEY** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список возможных возвращаемых значений см. в разделе [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameseticona--cwindowseticon"></a><a name="seticon"></a>CWindow::SetIcon  
 Задает значок, определяемый крупных или мелких значков окна `hIcon`.  
  
```
HICON SetIcon(HICON hIcon, BOOL bBigIcon = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hIcon`  
 [in] Дескриптор новый значок.  
  
 `bBigIcon`  
 [in] Если **TRUE** (значение по умолчанию), метод устанавливает крупных значков. В противном случае — задает мелкого значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значок "Назад".  
  
### <a name="remarks"></a>Примечания  
 `SetIcon`отправляет [WM_SETICON](http://msdn.microsoft.com/library/windows/desktop/ms632643) сообщения в окне.  
  
##  <a name="a-namesetmenua--cwindowsetmenu"></a><a name="setmenu"></a>CWindow::SetMenu  
 Изменяет текущее меню окна.  
  
```
BOOL SetMenu(HMENU hMenu) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms647995) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetparenta--cwindowsetparent"></a><a name="setparent"></a>CWindow::SetParent  
 Изменяет родительское окно.  
  
```
HWND SetParent(HWND hWndNewParent) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetParent](http://msdn.microsoft.com/library/windows/desktop/ms633541) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#32;](../../atl/codesnippet/cpp/cwindow-class_32.cpp)]  
  
##  <a name="a-namesetredrawa--cwindowsetredraw"></a><a name="setredraw"></a>CWindow::SetRedraw  
 Устанавливает или снимает флаг перерисовки путем отправки [WM_SETREDRAW](http://msdn.microsoft.com/library/windows/desktop/dd145219) сообщения в окне.  
  
```
void SetRedraw(BOOL bRedraw = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bRedraw`  
 [in] Указывает состояние флага перерисовки. Если **TRUE** (значение по умолчанию), перерисовки флаг; Если **FALSE**, флаг снят.  
  
### <a name="remarks"></a>Примечания  
 Вызов `SetRedraw` для разрешения смены перерисовку или для предотвращения изменения перерисовываться.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#33;](../../atl/codesnippet/cpp/cwindow-class_33.cpp)]  
  
##  <a name="a-namesetscrollinfoa--cwindowsetscrollinfo"></a><a name="setscrollinfo"></a>CWindow::SetScrollInfo  
 Задает параметры полосы прокрутки.  
  
```
int SetScrollInfo(  
    int nBar,
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetScrollInfo](http://msdn.microsoft.com/library/windows/desktop/bb787595) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetscrollposa--cwindowsetscrollpos"></a><a name="setscrollpos"></a>CWindow::SetScrollPos  
 Изменение положения ползунка полосы прокрутки.  
  
```
int SetScrollPos(  
    int nBar,
    int nPos,
    BOOL bRedraw = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetscrollrangea--cwindowsetscrollrange"></a><a name="setscrollrange"></a>CWindow::SetScrollRange  
 Изменяет диапазон значений для полосы прокрутки.  
  
```
BOOL SetScrollRange(  
    int nBar,
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetScrollRange](http://msdn.microsoft.com/library/windows/desktop/bb787599) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettimera--cwindowsettimer"></a><a name="settimer"></a>CWindow::SetTimer  
 Создает событие таймера.  
  
```
UINT SetTimer(  
    UINT nIDEvent,
    UINT nElapse,
    void (CALLBACK* lpfnTimer)(HWND, UINT, UINT, DWORD) = NULL) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetTimer](http://msdn.microsoft.com/library/windows/desktop/ms644906) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetwindowcontexthelpida--cwindowsetwindowcontexthelpid"></a><a name="setwindowcontexthelpid"></a>CWindow::SetWindowContextHelpId  
 Задает идентификатор контекста справки окна.  
  
```
BOOL SetWindowContextHelpId(DWORD dwContextHelpId) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowContextHelpId](http://msdn.microsoft.com/library/windows/desktop/bb762101) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetwindowlonga--cwindowsetwindowlong"></a><a name="setwindowlong"></a>CWindow::SetWindowLong  
 Задает 32-разрядное значение с указанным смещением в память открытое окно.  
  
```
LONG SetWindowLong(int nIndex, LONG dwNewLong) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Чтобы написать код, который совместим с 32-разрядной и 64-разрядных версиях Windows, используйте [CWindow::SetWindowLongPtr](#setwindowlongptr).  
  
##  <a name="a-namesetwindowlongptra--cwindowsetwindowlongptr"></a><a name="setwindowlongptr"></a>CWindow::SetWindowLongPtr  
 Изменяет атрибут указанного окна, а также задает значение с указанным смещением в открытое окно памяти.  
  
```
LONG_PTR SetWindowLongPtr(int nIndex, LONG_PTR dwNewLong) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowLongPtr](http://msdn.microsoft.com/library/windows/desktop/ms644898) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Эта функция замещает `CWindow::SetWindowLong` метод. Чтобы написать код, который совместим с 32-разрядной и 64-разрядных версиях Windows, используйте `CWindow::SetWindowLongPtr`.  
  
##  <a name="a-namesetwindowplacementa--cwindowsetwindowplacement"></a><a name="setwindowplacement"></a>CWindow::SetWindowPlacement  
 Задает состояние отображения и положения.  
  
```
BOOL SetWindowPlacement(const WINDOWPLACEMENT FAR* lpwndpl);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowPlacement](http://msdn.microsoft.com/library/windows/desktop/ms633544) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetwindowposa--cwindowsetwindowpos"></a><a name="setwindowpos"></a>CWindow::SetWindowPos  
 Задает размер, положение и Z-порядку.  
  
```
BOOL SetWindowPos(  
    HWND hWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags) throw();

BOOL SetWindowPos(  
    HWND hWndInsertAfter,
    LPCRECT lpRect,
    UINT nFlags) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Вторая версия этого метода использует [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, чтобы задать новое положение, ширину и высоту окна.  
  
##  <a name="a-namesetwindowrgna--cwindowsetwindowrgn"></a><a name="setwindowrgn"></a>CWindow::SetWindowRgn  
 Задает область окна, окна.  
  
```
int SetWindowRgn(HRGN hRgn, BOOL bRedraw = FALSE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowRgn](http://msdn.microsoft.com/library/windows/desktop/dd145102) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetwindowtexta--cwindowsetwindowtext"></a><a name="setwindowtext"></a>CWindow::SetWindowText  
 Изменяет текст окна.  
  
```
BOOL SetWindowText(LPCTSTR lpszString) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowText](http://msdn.microsoft.com/library/windows/desktop/ms633546) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#34;](../../atl/codesnippet/cpp/cwindow-class_34.cpp)]  
  
##  <a name="a-namesetwindowworda--cwindowsetwindowword"></a><a name="setwindowword"></a>CWindow::SetWindowWord  
 Задает 16-разрядное значение с указанным смещением в открытое окно память.  
  
```
WORD SetWindowWord(int nIndex, WORD wNewWord) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowcareta--cwindowshowcaret"></a><a name="showcaret"></a>CWindow::ShowCaret  
 Отображает системного курсора.  
  
```
BOOL ShowCaret() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ShowCaret](http://msdn.microsoft.com/library/windows/desktop/ms648406) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#35;](../../atl/codesnippet/cpp/cwindow-class_35.cpp)]  
  
##  <a name="a-nameshowownedpopupsa--cwindowshowownedpopups"></a><a name="showownedpopups"></a>CWindow::ShowOwnedPopups  
 Показывает или скрывает всплывающие окна, принадлежащие окна.  
  
```
BOOL ShowOwnedPopups(BOOL bShow = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ShowOwnedPopups](http://msdn.microsoft.com/library/windows/desktop/ms633547) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowscrollbara--cwindowshowscrollbar"></a><a name="showscrollbar"></a>CWindow::ShowScrollBar  
 Показывает или скрывает полосы прокрутки.  
  
```
BOOL ShowScrollBar(UINT nBar, BOOL bShow = TRUE) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ShowScrollBar](http://msdn.microsoft.com/library/windows/desktop/bb787601) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowwindowa--cwindowshowwindow"></a><a name="showwindow"></a>CWindow::ShowWindow  
 Задает состояние окна отображения.  
  
```
BOOL ShowWindow(int nCmdShow) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms633548) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#36;](../../atl/codesnippet/cpp/cwindow-class_36.cpp)]  
  
##  <a name="a-nameshowwindowasynca--cwindowshowwindowasync"></a><a name="showwindowasync"></a>CWindow::ShowWindowAsync  
 Задает состояние отображения окна, созданного в другом потоке.  
  
```
BOOL ShowWindowAsync(int nCmdShow) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ShowWindowAsync](http://msdn.microsoft.com/library/windows/desktop/ms633549) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameupdatewindowa--cwindowupdatewindow"></a><a name="updatewindow"></a>CWindow::UpdateWindow  
 Обновляет клиентскую область.  
  
```
BOOL UpdateWindow() throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [UpdateWindow](http://msdn.microsoft.com/library/windows/desktop/dd145167) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#37;](../../atl/codesnippet/cpp/cwindow-class_37.cpp)]  
  
##  <a name="a-namevalidaterecta--cwindowvalidaterect"></a><a name="validaterect"></a>CWindow::ValidateRect  
 Проверяет клиентской области в заданном прямоугольнике.  
  
```
BOOL ValidateRect(LPCRECT lpRect) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ValidateRect](http://msdn.microsoft.com/library/windows/desktop/dd145194) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namevalidatergna--cwindowvalidatergn"></a><a name="validatergn"></a>CWindow::ValidateRgn  
 Проверяет клиентской области в пределах указанной области.  
  
```
BOOL ValidateRgn(HRGN hRgn) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [ValidateRgn](http://msdn.microsoft.com/library/windows/desktop/dd145195) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namewinhelpa--cwindowwinhelp"></a><a name="winhelp"></a>CWindow::WinHelp  
 Запускает справку Windows.  
  
```
BOOL WinHelp(  
    LPCTSTR lpszHelp,
    UINT nCmd = HELP_CONTEXT,
    DWORD dwData = 0) throw();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

