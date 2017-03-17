---
title: "Класс CEdit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
dev_langs:
- C++
helpviewer_keywords:
- separators, in multiline edit controls
- text editors
- controls [MFC], edit
- text editors, CEdit class
- edit controls, classes
- multiline edit control
- CEdit class
- line separators in multiline edit controls
- edit controls
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
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
ms.openlocfilehash: 9c782e77b1fdb9026ee030238413955ba4d537e9
ms.lasthandoff: 02/24/2017

---
# <a name="cedit-class"></a>CEdit Class
Предоставляет функции элемента управления редактированием Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|Создает `CEdit` объект элемента управления.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|Определяет, можно ли отменить операцию управления редактированием.|  
|[CEdit::CharFromPos](#charfrompos)|Возвращает индексы строки и символ, ближайший к указанной позиции символа.|  
|[CEdit::Clear](#clear)|Удаляет (очистка) управления текущее выделение (если таковые имеются) в меню Правка.|  
|[CEdit::Copy](#copy)|Копирует текущее выделение (если таковые имеются) в элементе управления в буфер обмена в **CF_TEXT** формат.|  
|[CEdit::Create](#create)|Управления редактированием Windows создает и присоединяет его к `CEdit` объекта.|  
|[CEdit::Cut](#cut)|Удаляет (сокращает) управления текущее выделение (если таковые имеются) в меню Правка и копирует удаленный текст в буфер обмена в **CF_TEXT** формат.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Сбрасывает элемент управления (очистка) флаг отмены изменения.|  
|[CEdit::FmtLines](#fmtlines)|Задает включение мягкого разрыва строки символов или отключить в элементе управления многострочного редактирования.|  
|[CEdit::GetCueBanner](#getcuebanner)|Получает текст, который отображается в виде текста подсказки или совет, в элемент управления редактирования, если элемент управления является пустым и не имеет фокуса.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Определяет, отображается в первой строке элемента управления.|  
|[CEdit::GetHandle](#gethandle)|Получает дескриптор для памяти, выделенной для редактирования многострочного элемента управления.|  
|[CEdit::GetHighlight](#gethighlight)|Возвращает индексы начальный и конечный символы в диапазоне текста, который выделен в текущем элементе управления.|  
|[CEdit::GetLimitText](#getlimittext)|Получает максимальный объем текста, это `CEdit` может содержать.|  
|[CEdit::GetLine](#getline)|Извлекает строки текста из элемента управления.|  
|[CEdit::GetLineCount](#getlinecount)|Возвращает число строк в элементе управления edit несколько строк.|  
|[CEdit::GetMargins](#getmargins)|Возвращает левое и правое поля для этого `CEdit`.|  
|[CEdit::GetModify](#getmodify)|Определяет, были ли изменены содержимое элемента управления.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|Возвращает знак пароля, отображаются в элемент управления, когда пользователь вводит текст.|  
|[CEdit::GetRect](#getrect)|Возвращает прямоугольник, форматирование элемента управления.|  
|[CEdit::GetSel](#getsel)|Возвращает позицию первого и последнего символа текущего выделенного фрагмента в элемент управления редактированием.|  
|[CEdit::HideBalloonTip](#hideballoontip)|Скрывает все всплывающей подсказки, связанный с текущего элемента управления редактирования.|  
|[CEdit::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в элемент управления.|  
|[CEdit::LineFromChar](#linefromchar)|Получает номер строки, содержащей символ с указанным индексом.|  
|[CEdit::LineIndex](#lineindex)|Возвращает индекс символа строки внутри многострочного редактирования элемента управления.|  
|[CEdit::LineLength](#linelength)|Получает длину строки в элемент управления редактированием.|  
|[CEdit::LineScroll](#linescroll)|Прокрутка текста элемента управления редактированием несколько строк.|  
|[CEdit::Paste](#paste)|Вставляет данные из буфера обмена в элемент управления, расположенный в текущей позиции курсора. Данные вставляются только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.|  
|[CEdit::PosFromChar](#posfromchar)|Возвращает координаты верхнего левого угла символ с указанным индексом.|  
|[CEdit::ReplaceSel](#replacesel)|Заменяет текущее выделение в элементе управления редактирования с указанным текстом.|  
|[CEdit::SetCueBanner](#setcuebanner)|Задает текст, который отображается в виде текста подсказки или совет, в элемент управления редактирования, если элемент управления является пустым и не имеет фокуса.|  
|[CEdit::SetHandle](#sethandle)|Задает дескриптор к локальной памяти, который будет использоваться элементом управления многострочного редактирования.|  
|[CEdit::SetHighlight](#sethighlight)|Основные особенности диапазон текста, отображаемого в текущем поля ввода.|  
|[CEdit::SetLimitText](#setlimittext)|Задает максимальный объем текста, это `CEdit` может содержать.|  
|[CEdit::SetMargins](#setmargins)|Задает левое и правое поля для этого `CEdit`.|  
|[CEdit::SetModify](#setmodify)|Устанавливает или снимает флаг изменения элемента управления редактирования.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|Задает или удаляет символ пароля, отображаются в элемент управления, когда пользователь вводит текст.|  
|[CEdit::SetReadOnly](#setreadonly)|Задает состояние элемента управления только для чтения.|  
|[CEdit::SetRect](#setrect)|Задает прямоугольника форматирования элемента управления редактированием несколько строк и обновляет элемент управления.|  
|[CEdit::SetRectNP](#setrectnp)|Задает прямоугольника форматирования элемента управления редактированием многострочный без перерисовка окна элемента управления.|  
|[CEdit::SetSel](#setsel)|Выбирает диапазон символов в элемент управления редактированием.|  
|[CEdit::SetTabStops](#settabstops)|Поля ввода наборов табуляции в несколько строк.|  
|[CEdit::ShowBalloonTip](#showballoontip)|Отображает всплывающую подсказку, связанный с текущего элемента управления редактирования.|  
|[CEdit::Undo](#undo)|Отменяет последнюю операцию управления редактированием.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления редактированием является прямоугольной дочернее окно, в котором пользователь может вводить текст.  
  
 Элемент управления можно создать из шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CEdit` для создания `CEdit` , а затем вызвать [создать](#create) функции-члена для создания окна элемент управления и присоединить его к `CEdit` объекта.  
  
 Построение может быть задачей в класс, производный от `CEdit`. Создание конструктора для производного класса и вызове **создать** из внутри конструктора.  
  
 `CEdit`наследует существенные функциональные возможности из `CWnd`. Для установки и извлечения текста из `CEdit` , используйте `CWnd` функции-члены [SetWindowText](cwnd-class.md#setwindowtext) и [GetWindowText](cwnd-class.md#getwindowtext), который задать или получить все содержимое элемента управления редактирования, даже если это многострочный элемент управления. Строки текста в многострочном элементе управления разделяются последовательности знаков «\r\n». Кроме того, если многострочный элемент управления редактированием, get и set часть текста элемента управления путем вызова `CEdit` функции-члены [GetLine](#getline), [SetSel](#setsel), [GetSel](#getsel), и [ReplaceSel](#replacesel).  
  
 Если требуется для обработки сообщений Windows уведомлений, отправленных родительского элемента управления (обычно класс, производный от `CDialog`), добавление карты сообщение входа и обработчик сообщений функции-члена родительский класс для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**уведомления **(** *идентификатор, memberFxn***)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления поля ввода, отправку уведомления, и `memberFxn` имя родительской функции члена, написанный для обработки уведомления.  
  
 Прототип функции родительского выглядит следующим образом:  
  
 **afx_msg** void memberFxn **();**  
  
 Ниже приведен список потенциальных записей сопоставления сообщений и описание вариантов, в которых они были бы отправлены родительского.  
  
- **ON_EN_CHANGE** пользователя вступила в действие, которое может изменен текст в элемент управления редактированием. В отличие от **EN_UPDATE** , это уведомление отправляется уведомление после отображения обновлений Windows.  
  
- **ON_EN_ERRSPACE** поля ввода не удается выделить достаточно памяти для выполнения конкретного запроса.  
  
- **ON_EN_HSCROLL** пользователь щелкает элемент управления редактированием горизонтальной полосы прокрутки. Родительское окно получает уведомление до обновления экрана.  
  
- **ON_EN_KILLFOCUS** поля ввода теряет фокус ввода.  
  
- **ON_EN_MAXTEXT** текущей вставки превысило указанное количество символов для элемента управления редактирования и было усечено. Также отправляется, когда элемент управления не имеет **ES_AUTOHSCROLL** стиль и количество символов для вставки превышает ширину элемента управления. Также отправляется, когда элемент управления не имеет **ES_AUTOVSCROLL** стиль и общее число строк, возникающие в результате вставки текста превышает высоту элемента управления.  
  
- **ON_EN_SETFOCUS** посылается, когда элемент управления получает фокус ввода.  
  
- **ON_EN_UPDATE** управления правка собирается отобразить измененный текст. Отправлено после форматирования текста элемента управления, но до его экраны текст, чтобы размер окна может быть изменен, при необходимости.  
  
- **ON_EN_VSCROLL** пользователь щелкает элемент управления редактированием вертикальной полосы прокрутки. Родительское окно получает уведомление до обновления экрана.  
  
 При создании `CEdit` объекта в диалоговом окне, `CEdit` объект автоматически уничтожается, когда пользователь закрывает окно.  
  
 При создании `CEdit` из ресурса диалогового окна с помощью редактора диалоговых окон, `CEdit` объект автоматически уничтожается, когда пользователь закрывает окно.  
  
 При создании `CEdit` объекта в окне, необходимо уничтожить его. При создании `CEdit` объекта в стеке удаляется автоматически. При создании `CEdit` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь завершает Windows изменение элемента управления. Если выделять память в `CEdit` объекта, переопределить `CEdit` деструктор для удаления распределения.  
  
 Чтобы изменить стили, определенные в элемент управления редактированием (такие как **ES_READONLY**) определенных сообщений необходимо отправить элементу управления вместо [ModifyStyle](cwnd-class.md#modifystyle). В разделе [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о `CEdit`, см.:  
  
- [Элементы управления](../../mfc/controls-mfc.md)  
  
-   Статья базы знаний Q259949: INFO: SetCaretPos() — не соответствующие CEdit или элементы управления CRichEditCtrl  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="canundo"></a>CEdit::CanUndo  
 Эта функция вызывается для определения, если можно отменить последнюю операцию редактирования.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если последнюю операцию редактирования могут быть отменены путем вызова **отменить** функция-член; 0, если он не может быть отменено.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::Undo](#undo).  
  
##  <a name="cedit"></a>CEdit::CEdit  
 Создает объект `CEdit`.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [создать](#create) для создания окна редактирования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#1;](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>CEdit::CharFromPos  
 Эта функция вызывается для получения отсчитываемый от нуля и индексы символ знака ближайшего заданная точка в этом `CEdit` управления  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Координаты точки в клиентской области данного объекта `CEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс символа в младших **WORD**и индекс строки в высокого порядка **WORD**.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Эта функция-член будет доступен, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#3;](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>CEdit::Clear  
 Эта функция вызывается для удаления (clear) текущее выделение (если таковые имеются) в элементе управления.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Удаления, выполняемые **снимите** можно отменить, вызвав [отменить](#undo) функции-члена.  
  
 Чтобы удалить текущее выделение и поместите удаленные содержимое в буфер обмена, вызовите [Вырезать](#cut) функции-члена.  
  
 Дополнительные сведения см. в разделе [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#4;](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>CEdit::Copy  
 Эта функция вызывается для копирование текущего выделенного фрагмента (если таковые имеются) в буфер обмена в элементе управления **CF_TEXT** формат.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#5;](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>CEdit::Create  
 Управления редактированием Windows создает и присоединяет его к `CEdit` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления поля ввода. Примените любое сочетание [редактирование стилей](edit-styles.md) к элементу управления.  
  
 `rect`  
 Задает размер и положение элемента управления поля ввода. Может быть `CRect` объекта или `RECT` структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления поля ввода (обычно `CDialog`). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления поля ввода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CEdit` объекта в два этапа. Во-первых, вызовите `CEdit` конструктор и затем вызвать **создать**, который создает управления редактированием Windows и присоединяет его к `CEdit` объекта.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), и [WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) сообщений для элемента управления поля ввода.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), и [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CEdit`, добавить схему сообщения в новый класс и переопределить выше функции-члены обработчик сообщений. Переопределение `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Примените следующий [стили окна](window-styles.md) для элемента управления.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_GROUP** для группирования элементов управления  
  
- **WS_TABSTOP** для включения управления редактированием в порядке табуляции  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#2;](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>CEdit::Cut  
 Эта функция вызывается для удаления (Вырезать) текущее выделение (если таковые имеются) в элементе управления и скопируйте удаленный текст в буфер обмена в **CF_TEXT** формат.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Примечания  
 Удаления, выполняемые **Вырезать** можно отменить, вызвав [отменить](#undo) функции-члена.  
  
 Чтобы удалить текущее выделение без помещения удаленный текст в буфер обмена, вызовите [снимите](#clear) функции-члена.  
  
 Дополнительные сведения см. в разделе [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit №&6;](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>CEdit::EmptyUndoBuffer  
 Эта функция вызывается для сброса (Очистить) флаг отмены элемента управления.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Примечания  
 Элемент управления поля ввода будет невозможно отменить последнюю операцию. Флаг отмены всякий раз, когда операции в элементе управления редактирования могут быть отменены.  
  
 Флаг отмены будет автоматически очищен всякий раз, когда [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) или [SetHandle](#sethandle) `CWnd` вызываются функции-члены.  
  
 Дополнительные сведения см. в разделе [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#7;](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>CEdit::FmtLines  
 Вызовите эту функцию для задания включения мягкого разрыва строки символов или отключить в элементе управления многострочного редактирования.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>Параметры  
 *bAddEOL*  
 Указывает, должны быть вставлены мягкого разрыва строки символов. Значение **TRUE** вставляет символы; значение **FALSE** удаляет их.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все форматирование происходит; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Мягкий перенос состоит из двух символы возврата каретки и перевода строки вставлены в конце строки, разорвано из-за переноса слов. Разрыв строки жесткого состоит из одного символы возврата каретки и перевода строки. Строки, оканчивающиеся разрывом строки жесткого не подвержены `FmtLines`.  
  
 Windows будет отвечать только в том случае, если `CEdit` объект является элементом управления многострочного редактирования.  
  
 `FmtLines`влияет только на буфер, возвращенный при [GetHandle](#gethandle) и текст, возвращенный [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627). Он не оказывает влияния на отображение текста в элементе управления редактирования.  
  
 Дополнительные сведения см. в разделе [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit №&8;](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>CEdit::GetCueBanner  
 Получает текст, который отображается в виде текста подсказки или совет, в элемент управления редактированием при пустом элементе управления.  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lpszText`  
 Указатель на строку, содержащую текст подсказки.  
  
 [in] `cchText`  
 Число символов, которые могут быть получены. Это число включает конечный символ `NULL` символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой перегрузке `true` Если метод выполнен успешно; в противном случае `false`.  
  
 Второй перегрузке [CString](../../atl-mfc-shared/using-cstring.md) , содержащее текст подсказки, если метод выполнен успешно; в противном случае — пустая строка («»).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) макрос.  
  
##  <a name="getfirstvisibleline"></a>CEdit::GetFirstVisibleLine  
 Эта функция используется для определения верхней строкой видимым в элементе управления редактирования.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первой видимой строке. Однострочный элементах управления для редактирования возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit №&9;](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>CEdit::GetHandle  
 Эта функция вызывается для получения дескриптора для памяти, выделенной для редактирования многострочного элемента управления.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор локальной памяти, который идентифицирует буфер, содержащий содержимое элемента управления поля ввода. Если возникает ошибка, такие как отправка сообщения в одну строку ввода, возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор является дескриптором локальной памяти и могут быть использованы любым из **локального** функции памяти Windows, которые принимают локальной памяти обрабатывать как параметр.  
  
 **GetHandle** обрабатывается только несколько строк ввода.  
  
 Вызов **GetHandle** редактирование многострочных элемента управления в диалоговом окне только в том случае, если диалоговое окно было создано в **DS_LOCALEDIT** установленным флагом стиля. Если **DS_LOCALEDIT** стиля не задано, будет по-прежнему получить ненулевое возвращаемое значение, но вы не сможете использовать возвращаемое значение.  
  
> [!NOTE]
> **GetHandle** не будет работать с Windows 95/98. При вызове метода **GetHandle** в Windows 95/98, он будет возвращать **NULL**. **GetHandle** будет работать, как описано в Windows NT 3.51 и более поздние версии.  
  
 Дополнительные сведения см. в разделе [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#10;](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>CEdit::GetHighlight  
 Возвращает индексы первый и последний символы в диапазоне текста, который выделен в текущем элементе управления.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pichStart`|Отсчитываемый от нуля индекс первого символа в диапазоне текста, который будет выделен.|  
|[выходной] `pichEnd`|Отсчитываемый от нуля индекс последнего символа в диапазоне текста, который будет выделен.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>CEdit::GetLimitText  
 Эта функция-член для получения текста ограничение для этого вызова `CEdit` объекта.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий текст предельный размер в байтах для данного `CEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
 Ограничение текста — максимальный объем текста, в байтах, который может принимать элемент управления для редактирования.  
  
> [!NOTE]
>  Эта функция-член будет доступен, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&11;](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>CEdit::GetLine  
 Эта функция вызывается для получения строки текста из элемента управления и помещает его в `lpszBuffer`.  
  
```  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает номер строки для извлечения из многострочного редактирования элемента управления. Номера строк отсчитываются от нуля; значение 0 задает первую строку. Этот параметр обрабатывается элементом управления одной строкой.  
  
 `lpszBuffer`  
 Указывает для буфера, который получает копию строки. Первое слово буфера необходимо указать максимальное количество символов, которые могут быть скопированы в буфер.  
  
 `nMaxLength`  
 Указывает максимальное число байтов, которые могут быть скопированы в буфер. `GetLine`Это значение будет помещено в первом слове `lpszBuffer` перед вызовом для Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число фактически скопированных байтов. Возвращаемое значение равно 0, если номер строки, заданный параметром `nIndex` больше, чем число строк в элементе управления.  
  
### <a name="remarks"></a>Примечания  
 Скопированные строки не содержит символ конечное значение null.  
  
 Дополнительные сведения см. в разделе [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>CEdit::GetLineCount  
 Эта функция используется для получения числа строк в элементе управления edit несколько строк.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поля ввода integer, содержащее количество строк в несколько строк. Если текст не было введено в элемент управления, возвращаемое значение — 1.  
  
### <a name="remarks"></a>Примечания  
 `GetLineCount`обрабатывается только элементами управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#12;](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>CEdit::GetMargins  
 Вызовите эту функцию-член для получения левого и правого полей поля ввода.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина левого поля в младших **WORD** и ширину правого поля высокого порядка **WORD**.  
  
### <a name="remarks"></a>Примечания  
 Поля измеряются в пикселях.  
  
> [!NOTE]
>  Эта функция-член будет доступен, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="getmodify"></a>CEdit::GetModify  
 Эта функция вызывается для определения, были ли изменены содержимое элемента управления.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если содержимое элемента управления редактирования были изменены; 0, если они остаются без изменений.  
  
### <a name="remarks"></a>Примечания  
 Windows поддерживает внутреннего флага, показывающее, были ли изменены содержимое элемента управления поля ввода. Данный флаг снят, когда создается элемент управления для редактирования и также может быть очищен путем вызова [SetModify](#setmodify) функции-члена.  
  
 Дополнительные сведения см. в разделе [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#13;](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>CEdit::GetPasswordChar  
 Эта функция вызывается для получения пароля символ, который отображается в элемент управления, когда пользователь вводит текст.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает символ для отображения вместо символа, который введен пользователем. Возвращаемое значение является `NULL` Если знака пароля не существует.  
  
### <a name="remarks"></a>Примечания  
 При создании элемента управления поля ввода с **ES_PASSWORD** стиль, библиотеки DLL, которая поддерживает элемент управления определяет знак пароля по умолчанию. Манифест или [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) метод определяет, какие библиотеки DLL поддерживает элемент управления для редактирования. Если user32.dll поддерживает элемент управления для редактирования, знак пароля по умолчанию является символ ЗВЕЗДОЧКИ ("*", U +&002;A). Если comctl32.dll версии 6 поддерживает элемент управления поля ввода, символ по умолчанию — ЧЕРНЫЙ КРУГ («●», U + 25CF). Дополнительные сведения о поддерживающий DLL и версии см. Общие элементы управления [оболочка и версии общих элементов управления](http://msdn.microsoft.com/library/windows/desktop/bb776779).  
  
 Этот метод отправляет [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#14;](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>CEdit::GetRect  
 Эта функция вызывается для получения прямоугольника форматирования из элемента управления.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуру, которая получает прямоугольника форматирования.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольника форматирования является ограничивающим прямоугольником текста, которая не зависит от размера окна элемента управления редактирования.  
  
 Прямоугольника форматирования элемента управления редактированием несколько строк могут быть изменены [SetRect](#setrect) и [SetRectNP](#setrectnp) функции-члены.  
  
 Дополнительные сведения см. в разделе [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::LimitText](#limittext).  
  
##  <a name="getsel"></a>CEdit::GetSel  
 Эта функция вызывается для получения начала и окончания позиций символов текущее выделение (если таковые имеются) в элемент управления, с помощью возвращаемого значения или параметров.  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartChar`  
 Ссылка на целое число, будут получать позицию первого символа в выделенном фрагменте.  
  
 `nEndChar`  
 Ссылка на целое число, будут получать позицию первого символа невыбранные за пределами текущего выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версия, которая возвращает `DWORD` возвращает значение, содержащее начальную позицию в младшее слово и позиция первого знака невыбранные после завершения выбора в старшее слово.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#15;](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>CEdit::HideBalloonTip  
 Скрывает все всплывающей подсказки, связанный с текущего элемента управления редактирования.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция отправляет [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="limittext"></a>CEdit::LimitText  
 Эта функция вызывается для ограничения длины текста, который пользователь может ввести в элемент управления.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nChars`  
 Указывает длину (в байтах), которые пользователь может вводить текст. Если этот параметр равен 0, значение длины текста **UINT_MAX** байт. Это поведение установлено по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Изменение текста ограничения ограничивает только текст, который может быть введено пользователем. Он не влияет на любой текст уже в элементе управления, а также влияет на длину текста, копируются в элемент управления поля ввода, [SetWindowText](cwnd-class.md#setwindowtext) функции-члена `CWnd`. Если приложение использует `SetWindowText` поместить текст в элемент управления редактированием, чем указано в вызове функции `LimitText`, пользователь может удалять любой текст в поле редактирования. Однако ограничение текст не позволит пользователю заменять существующий текст новым текстом, если удаление выделенного вызывает текста нарушит ограничение текста.  
  
> [!NOTE]
>  В Win32 (Windows NT и Windows 95/98) [SetLimitText](#setlimittext) заменяет эту функцию.  
  
 Дополнительные сведения см. в разделе [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&17;](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>CEdit::LineFromChar  
 Эта функция вызывается для получения номер строки, содержащей символ с указанным индексом.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс значение требуемого символа в тексте элемента управления поля ввода, или значение -1. Если `nIndex` –&1;, он указывает текущей строки, то есть строка, содержащая курсор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля номер строки, содержащей указанный индекс символа `nIndex`. Если `nIndex` –&1;, возвращается номер строки, содержащей первого символа выделения. Если не выбрано, возвращается текущий номер строки.  
  
### <a name="remarks"></a>Примечания  
 Индекс символа — количество символов с начала элемента управления.  
  
 Эта функция-член используется только элементами управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&18;](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>CEdit::LineIndex  
 Эта функция вызывается для извлечения индекса символа строки внутри многострочного редактирования элемента управления.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nLine`  
 Содержит значение индекса для нужной строке в тексте элемента управления поля ввода, или значение -1. Если `nLine` –&1;, он указывает текущей строки, то есть строка, содержащая курсор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс строки, указанной в `nLine` или -1, если номер строки больше, чем число строк в элементе управления.  
  
### <a name="remarks"></a>Примечания  
 Индекс знака является количество символов с начала элемента управления поля ввода на указанную строку.  
  
 Эта функция-член обрабатывается только элементы управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&19;](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>CEdit::LineLength  
 Получает длину строки в элемент управления редактированием.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nLine`  
 Отсчитываемый от нуля индекс символа в строке, длина которого требуется получить. Значение по умолчанию — -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Однострочный элементах управления для редактирования, возвращаемое значение — это длина в `TCHAR`s текста в элементе управления.  
  
 Для многострочных полей редактирования, возвращаемое значение — это длина в `TCHAR`s из строки, указанной в `nLine` параметр. Для [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] текст, длина — число байтов в строке; для текста в Юникоде, длина — число символов в строке. Длина отсутствует символ возврата каретки в конце строки.  
  
 Если `nLine` параметр больше, чем количество символов в элементе управления, возвращаемое значение равно нулю.  
  
 Если `nLine` параметр –&1;, возвращается число невыбранные символов в строки, содержащие выбранные символы. Например если выделение распространяется из одной строки через восьмой символ следующей строки в конце четвертый символ, возвращаемое значение равно 10. То есть три символов в первой строке и семь на следующем.  
  
 Дополнительные сведения о `TCHAR` см. в разделе `TCHAR` строк в таблице [типы данных Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживается [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>CEdit::LineScroll  
 Эта функция вызывается для прокрутки элемента управления редактированием многострочный текст.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nLines`  
 Указывает количество строк для прокрутки по вертикали.  
  
 `nChars`  
 Указывает количество позиций знаков для прокрутки по горизонтали. Это значение игнорируется, если для редактирования элемента управления либо **ES_RIGHT** или **ES_CENTER** стиль.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Элемент управления поля ввода не вертикальную прокрутку, после последней строки текста в элементе управления. Если текущей строки и количество строк, определяемое `nLines` превышает общее число строк в элементе управления, значение корректируется, чтобы последняя строка элемента управления может прокручиваться в верхней части окна управления редактированием.  
  
 `LineScroll`можно использовать для прокрутки по горизонтали после последнего символа все строки.  
  
 Дополнительные сведения см. в разделе [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>CEdit::Paste  
 Эта функция вызывается для вставки данных из буфера обмена в `CEdit` в позиции курсора.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Примечания  
 Данные вставляются только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.  
  
 Дополнительные сведения см. в разделе [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&20;](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>CEdit::PosFromChar  
 Эта функция вызывается для получения позиции (верхний левый угол) определенный символ в рамках этого `CEdit` объекта.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Отсчитываемый от нуля индекс указанного символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Координаты верхнего левого угла символ `nChar`.  
  
### <a name="remarks"></a>Примечания  
 Символ, указанный, предоставив его с нуля значение. Если `nChar` больше индекса последнего символа в этом `CEdit` объекта, возвращаемое значение указывает координаты позиции после последнего символа в этом `CEdit` объекта.  
  
> [!NOTE]
>  Эта функция-член будет доступен, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::LineFromChar](#linefromchar).  
  
##  <a name="replacesel"></a>CEdit::ReplaceSel  
 Вызывайте эту функцию, чтобы заменить текущее выделение в элемент управления текст, заданный параметром `lpszNewText`.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszNewText`  
 Указывает нулем строка, содержащая текст для замены.  
  
 `bCanUndo`  
 Чтобы указать, что эта функция может быть отменено, значение этого параметра для **TRUE** . Значение по умолчанию — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Заменяет только часть текста в элементе управления редактирования. Если вы хотите заменить весь текст, используйте [CWnd::SetWindowText](cwnd-class.md#setwindowtext) функции-члена.  
  
 Если не выделен текущей, текст замены вставляется в текущую позицию курсора.  
  
 Дополнительные сведения см. в разделе [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::LineIndex](#lineindex).  
  
##  <a name="setcuebanner"></a>CEdit::SetCueBanner  
 Задает текст, который отображается в виде подсказки текст или совет, изменения управления, когда элемент управления является пустым.  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
 Указатель на строку, содержащую подсказки для отображения в элементе управления.  
  
 [in] `fDrawWhenFocused`  
 Если `false`, баннер подсказки не отображается, когда пользователь щелкает поле редактирования и фокуса элемента управления.  
  
 Если `true`, рисуется баннер подсказки, даже в том случае, если элемент управления имеет фокус. Баннер подсказки исчезает, когда пользователь начинает вводить в элементе управления.  
  
 Значение по умолчанию — `false`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) макрос.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется [CEdit::SetCueBanner](#setcuebanner) метод.  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>CEdit::SetHandle  
 Эта функция вызывается для задания к локальной памяти, который будет использоваться элементом управления многострочного редактирования.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>Параметры  
 *hBuffer*  
 Содержит дескриптор локальной памяти. Этот дескриптор должен быть создан предыдущим вызовом [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows с помощью функции **LMEM_MOVEABLE** флага. Предполагается, что память содержит строку с завершающим нулем. Если это не так, первый байт выделенной памяти должно быть равным 0.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления поля ввода будет использовать этот буфер для хранения текста, выделенного в настоящий момент вместо выделения собственного буфера.  
  
 Эта функция-член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Прежде чем приложение задает новый дескриптор памяти, следует использовать [GetHandle](#gethandle) получить дескриптор текущий буфер памяти и освобождения этой памяти с помощью функции-члена **LocalFree** функции Windows.  
  
 `SetHandle`Очищает буфер отмены ( [CanUndo](#canundo) функция-член возвращает 0) и флаг внутреннего изменения ( [GetModify](#getmodify) функция-член возвращает 0). Окно управления редактированием перерисовывается.  
  
 Можно использовать эту функцию-член в элементе управления edit несколько строк в диалоговом окне только в том случае, если вы создали диалогового окна с **DS_LOCALEDIT** установленным флагом стиля.  
  
> [!NOTE]
> **GetHandle** не будет работать с Windows 95/98. При вызове метода **GetHandle** в Windows 95/98, он будет возвращать **NULL**. **GetHandle** будет работать, как описано в Windows NT 3.51 и более поздние версии.  
  
 Дополнительные сведения см. в разделе [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), и [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#22;](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>CEdit::SetHighlight  
 Основные особенности диапазон текста, отображаемого в текущем поля ввода.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `ichStart`|Отсчитываемый от нуля индекс первого символа в диапазоне для выделения текста.|  
|[in] `ichEnd`|Отсчитываемый от нуля индекс последнего символа в диапазоне для выделения текста.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlimittext"></a>CEdit::SetLimitText  
 Вызовите эту функцию-член ограничение текст для этого `CEdit` объекта.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `nMax`  
 Новое ограничение текст в символах.  
  
### <a name="remarks"></a>Примечания  
 Ограничение текста — максимальный объем текста, символов, которые может принимать элемент управления для редактирования.  
  
 Изменение текста ограничения ограничивает только текст, который может быть введено пользователем. Он не влияет на любой текст уже в элементе управления, а также влияет на длину текста, копируются в элемент управления поля ввода, [SetWindowText](cwnd-class.md#setwindowtext) функции-члена `CWnd`. Если приложение использует `SetWindowText` поместить текст в элемент управления редактированием, чем указано в вызове функции `LimitText`, пользователь может удалять любой текст в поле редактирования. Однако ограничение текст не позволит пользователю заменять существующий текст новым текстом, если удаление выделенного вызывает текста нарушит ограничение текста.  
  
 Эта функция заменяет [LimitText](#limittext) в Win32.  
  
 Дополнительные сведения см. в разделе [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmargins"></a>CEdit::SetMargins  
 Вызовите этот метод, чтобы задать левое и правое поля поля ввода.  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>Параметры  
 *nLeft*  
 Ширина нового левого поля в пикселях.  
  
 *nRight*  
 Ширина нового правого поля в пикселях.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Эта функция-член будет доступен, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmodify"></a>CEdit::SetModify  
 Эта функция используется для установки или снятия измененного флага для элемента управления.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Значение **TRUE** указывает, что текст был изменен, а значение **FALSE** указывает, он не меняется. По умолчанию значение измененного флага.  
  
### <a name="remarks"></a>Примечания  
 Измененный флаг указывает, был изменен ли текст в элементе управления редактирования. Автоматически устанавливается каждый раз, когда пользователь изменяет текст. Ее значение может быть получено с [GetModify](#getmodify) функции-члена.  
  
 Дополнительные сведения см. в разделе [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::GetModify](#getmodify).  
  
##  <a name="setpasswordchar"></a>CEdit::SetPasswordChar  
 Эта функция используется для установки или удаления знака пароля отображается в элементе управления редактирования при вводе пользователем текста.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>Параметры  
 *CH*  
 Указывает символ для отображения вместо символа, введенного пользователем. Если *ch* равно 0, отображаются фактические символы, введенный пользователем.  
  
### <a name="remarks"></a>Примечания  
 Если задан символ пароля, этот символ отображается для каждого символьные типы пользователя.  
  
 Эта функция-член не влияет на несколько строк элемент управления.  
  
 Когда `SetPasswordChar` вызывается функция-член, `CEdit` обновление видны все символы, символ, указанный с помощью *ch*.  
  
 Если элемент управления поля ввода, создается с [ES_PASSWORD](edit-styles.md) , знак пароля по умолчанию задан стиль звездочку ( ** \* **). Этот стиль удаляется, если `SetPasswordChar` вызывается с *ch* равным 0.  
  
 Дополнительные сведения см. в разделе [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit №&16;](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>CEdit::SetReadOnly  
 Вызывает эту функцию для задания состояния элемента управления только для чтения.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bReadOnly`  
 Указывает, следует ли установка или удаление состояния только для чтения элемент управления для редактирования. Значение **TRUE** задает состояние только для чтения; значение **FALSE** задает состояние для чтения и записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно, или 0, если ошибка возникает.  
  
### <a name="remarks"></a>Примечания  
 Текущее значение параметра можно найти с помощью тестирования [ES_READONLY](edit-styles.md) флаг в значение, возвращаемое [CWnd::GetStyle](cwnd-class.md#getstyle).  
  
 Дополнительные сведения см. в разделе [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#23;](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>CEdit::SetRect  
 Эта функция вызывается для указания размеров прямоугольника с помощью по указанным координатам.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуры или `CRect` объект, который определяет новые размеры прямоугольника форматирования.  
  
### <a name="remarks"></a>Примечания  
 Этот член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Используйте `SetRect` форматирования управления edit прямоугольник несколько строк. Прямоугольника форматирования является ограничивающим прямоугольником текста, которая не зависит от размера окна элемента управления редактирования. При создании элемента управления поля ввода, прямоугольника форматирования совпадает клиентской области окна элемента управления редактирования. С помощью `SetRect` функции-члена, приложение может установить прямоугольника форматирования больше или меньше окна управления редактированием.  
  
 Если полосы прокрутки элемента управления поля ввода, текст будет обрезан, не заключаются в оболочку, если форматирования прямоугольника становится больше, чем окна. Если элемент управления поля ввода содержит границы, прямоугольника форматирования уменьшается размер границы. Если изменить возвращаемый прямоугольник `GetRect` функция-член, размер границы необходимо удалить, прежде чем передать прямоугольника для `SetRect`.  
  
 Когда `SetRect` вызывается элемент управления поля ввода в текст также переформатированы и повторно.  
  
 Дополнительные сведения см. в разделе [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#24;](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>CEdit::SetRectNP  
 Вызовите эту функцию для задания прямоугольника форматирования элемента управления редактированием несколько строк.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуры или `CRect` объект, который определяет новые размеры прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольника форматирования является ограничивающим прямоугольником текста, которая не зависит от размера окна элемента управления редактирования.  
  
 `SetRectNP`идентичен `SetRect` функция-член, но не перерисовке окна управления редактированием.  
  
 При создании элемента управления поля ввода, прямоугольника форматирования совпадает клиентской области окна элемента управления редактирования. Путем вызова `SetRectNP` функции-члена, приложение может установить прямоугольника форматирования больше или меньше окна управления редактированием.  
  
 Если полосы прокрутки элемента управления поля ввода, текст будет обрезан, не заключаются в оболочку, если форматирования прямоугольника становится больше, чем окна.  
  
 Этот член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::SetRect](#setrect).  
  
##  <a name="setsel"></a>CEdit::SetSel  
 Эта функция используется для выбора диапазона символов в элемент управления редактированием.  
  
```  
void SetSel(
    DWORD dwSelection,  
    BOOL bNoScroll = FALSE);

 
void SetSel(
    int nStartChar,  
    int nEndChar,  
    BOOL bNoScroll = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *dwSelection*  
 Указывает начальную позицию в младшее слово и конечную позицию в старшее слово. Если младшее слово равен 0 и старшее слово – 1, выбирается весь текст в элементе управления. Младшее слово –&1;, удаляются все текущее выделение.  
  
 *bNoScroll*  
 Указывает, является ли курсор должен выполнить прокрутку в представлении. Если **FALSE**, курсор в области просмотра. Если **TRUE**, курсор не в области просмотра.  
  
 `nStartChar`  
 Указывает начальную позицию. Если `nStartChar` равно 0 и `nEndChar` – 1, все выбранные текст в элементе управления. Если `nStartChar` –&1;, удаляется любой текущий выбор.  
  
 `nEndChar`  
 Указывает конечную позицию.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEdit::GetSel](#getsel).  
  
##  <a name="settabstops"></a>CEdit::SetTabStops  
 Вызывайте эту функцию, чтобы установить позицию табуляции в элементе управления edit несколько строк.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Параметры  
 `cxEachStop`  
 Указывает, что позиции табуляции для установки на каждом `cxEachStop` единицы диалогового окна.  
  
 `nTabStops`  
 Указывает номер позиции табуляции, содержащихся в `rgTabStops`. Это число должно быть больше 1.  
  
 `rgTabStops`  
 Указывает на массив целых чисел без знака, указывая на вкладке останавливается в единицы диалогового окна. Единица диалогового окна — горизонтальное или вертикальное расстояние. Четверть текущей единице измерения базового ширину диалогового окна равно единице горизонтального диалоговое окно, и 1 единица вертикальной диалогового окна равен одну восьмую Текущая единица высота основы диалоговое окно. Базовые единицы диалогового окна вычисляются на основе высота и ширина текущего системного шрифта. **GetDialogBaseUnits** функции Windows возвращает единицу текущего диалогового окна в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если были установлены вкладок; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При копировании текста в элемент управления редактирование многострочных любой символ табуляции в тексте вызовет пространства создаваться до следующей позиции табуляции.  
  
 Чтобы установить табуляции размером 32 единицы диалогового окна по умолчанию, вызовите версию без параметров эта функция-член. Чтобы установить позицию табуляции до размера, 32, вызовите версию с `cxEachStop` параметр. Чтобы установить табуляции в массив размеров, следует используйте версию с двумя параметрами.  
  
 Эта функция-член обрабатывается только элементы управления редактирования несколько строк.  
  
 `SetTabStops`не будут перерисовываться автоматически окна редактора. При изменении позиции табуляции для текста в элементе управления уже вызвать [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) перерисовка окна редактора.  
  
 Дополнительные сведения см. в разделе [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) и [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CEditView::SetTabStops](ceditview-class.md#settabstops).  
  
##  <a name="showballoontip"></a>CEdit::ShowBalloonTip  
 Отображает всплывающую подсказку, связанный с текущего элемента управления редактирования.  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pEditBalloonTip`|Указатель на [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) структура, описывающая всплывающая подсказка.|  
|[in] `lpszTitle`|Указатель на строку Юникода, содержащая заголовок окна всплывающей подсказки.|  
|[in] `lpszText`|Указатель на строку Юникода, содержащая текст всплывающей подсказки.|  
|[in] `ttiIcon`|`INT` , Указывающий тип значка, связываемый с всплывающей подсказки. Значение по умолчанию — `TTI_NONE`. Дополнительные сведения см. в разделе `ttiIcon` членом [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция отправляет [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) макрос.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_cedit`, который используется для доступа к текущей управления редактирования. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода отображает всплывающую подсказку для элемента управления. [CEdit::ShowBalloonTip](#showballoontip) метод задает текст заголовок и всплывающие подсказки.  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>CEdit::Undo  
 Эта функция вызывается для отмены последней операции управления редактированием.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для элемента управления редактирования одной строки возвращаемое значение всегда равно ненулевое значение. Для элемента управления редактирования несколько строк, возвращается ненулевое значение, если операция отмены выполнена успешно, или 0, если происходит сбой операции отмены.  
  
### <a name="remarks"></a>Примечания  
 Операции отмены также могут быть отменены. Например, можно восстановить удаленный текст с первого вызова **отменить**. При условии, что нет промежуточные операции редактирования, можно удалить текст снова с помощью второго вызова **отменить**.  
  
 Дополнительные сведения см. в разделе [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit&#25;](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CALCDRIV](../../visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](cwnd-class.md)   
 [Класс CButton](cbutton-class.md)   
 [CComboBox-класс](ccombobox-class.md)   
 [CListBox-класс](clistbox-class.md)   
 [Класс CScrollBar](cscrollbar-class.md)   
 [Класс CStatic](cstatic-class.md)   
 [CDialog-класс](cdialog-class.md)

