---
title: "Класс CEdit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4418f20b267218b761dd6637762df1b420e9ac6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cedit-class"></a>CEdit Class
Предоставляет функции элемента управления редактированием Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|Создает `CEdit` объект элемента управления.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|Определяет, можно ли отменить операцию управления редактирования.|  
|[CEdit::CharFromPos](#charfrompos)|Возвращает индексы строку и символ, ближайший к указанной позиции знака.|  
|[CEdit::Clear](#clear)|Удаление (очищает) управлять текущее выделение (если таковые имеются) в режиме изменения.|  
|[CEdit::Copy](#copy)|Копирует текущее выделение (если таковые имеются) в поле редактирования в буфер обмена в **CF_TEXT** формат.|  
|[CEdit::Create](#create)|Создает элемент управления редактирования Windows и прикрепляет его к `CEdit` объекта.|  
|[CEdit::Cut](#cut)|(Порезов) удаляет текущее выделение (если таковые имеются) в режиме изменения управления и копирует удаленный текст в буфер обмена в **CF_TEXT** формат.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Сброс (очистка) флаг отмены изменения элемента управления.|  
|[CEdit::FmtLines](#fmtlines)|Задает включение мягкого разрыва строки символов или отключить в элементе управления редактирования несколько строк.|  
|[CEdit::GetCueBanner](#getcuebanner)|Получает текст, отображаемый в качестве текст подсказки, то подсказки в элемент управления редактированием, когда элемент управления является пустым и не имеет фокуса.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Определяет верхний видимой строки ввода.|  
|[CEdit::GetHandle](#gethandle)|Получает дескриптор памяти, выделенной для элемента управления редактирования несколько строк.|  
|[CEdit::GetHighlight](#gethighlight)|Возвращает индексы начального и конечного символов в диапазоне, выделенного в текущий элемент управления редактирования текста.|  
|[CEdit::GetLimitText](#getlimittext)|Получает максимальный объем текста, это `CEdit` может содержать.|  
|[CEdit::GetLine](#getline)|Получает строку текста из элемента управления.|  
|[CEdit::GetLineCount](#getlinecount)|Возвращает число строк в элементе управления edit несколько строк.|  
|[CEdit::GetMargins](#getmargins)|Возвращает левое и правое поля для данного `CEdit`.|  
|[CEdit::GetModify](#getmodify)|Определяет, были ли изменены содержимое элемента управления edit.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|Получает пароль знак, используемый в элемент управления редактированием, когда пользователь вводит текст.|  
|[CEdit::GetRect](#getrect)|Возвращает прямоугольник, форматирования элемента управления edit.|  
|[CEdit::GetSel](#getsel)|Возвращает позицию текущего выделенного фрагмента в элемент управления редактированием первым и последним символом.|  
|[CEdit::HideBalloonTip](#hideballoontip)|Скрывает любой всплывающей подсказке, связанной с текущего элемента управления edit.|  
|[CEdit::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в элемент управления.|  
|[CEdit::LineFromChar](#linefromchar)|Возвращает номер строки в строку, содержащую символ с указанным индексом.|  
|[CEdit::LineIndex](#lineindex)|Возвращает индекс символа строки внутри многострочного редактирования элемента управления.|  
|[CEdit::LineLength](#linelength)|Получает длину строки в элемент управления редактированием.|  
|[CEdit::LineScroll](#linescroll)|Прокручивает текст элемента управления редактированием несколько строк.|  
|[CEdit::Paste](#paste)|Вставляет данные из буфера обмена в элемент управления, расположенный в текущей позиции курсора. Вставляются данные только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.|  
|[CEdit::PosFromChar](#posfromchar)|Извлекает координаты левого верхнего угла символ с указанным индексом.|  
|[CEdit::ReplaceSel](#replacesel)|Заменяет текущее выделение в элемент управления редактированием с указанным текстом.|  
|[CEdit::SetCueBanner](#setcuebanner)|Задает текст, отображаемый в качестве текст подсказки, то подсказки в элемент управления редактированием, когда элемент управления является пустым и не имеет фокуса.|  
|[CEdit::SetHandle](#sethandle)|Задает дескриптор к локальной памяти, используемого элементом управления редактирования несколько строк.|  
|[CEdit::SetHighlight](#sethighlight)|Выделяет текст, отображаемый в текущий диапазон поля ввода.|  
|[CEdit::SetLimitText](#setlimittext)|Задает максимальный объем текста, это `CEdit` может содержать.|  
|[CEdit::SetMargins](#setmargins)|Задает левое и правое поля для этого `CEdit`.|  
|[CEdit::SetModify](#setmodify)|Устанавливает или снимает флаг изменения элемента управления редактирования.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|Задает или удаляет символ пароля, отображаются в элемент управления редактированием, когда пользователь вводит текст.|  
|[CEdit::SetReadOnly](#setreadonly)|Задает состояние элемента управления edit только для чтения.|  
|[CEdit::SetRect](#setrect)|Задает прямоугольника форматирования элемента управления редактированием несколько строк и обновляет элемент управления.|  
|[CEdit::SetRectNP](#setrectnp)|Задает прямоугольника форматирования элемента управления редактированием несколько строк без перерисовки окна элемента управления.|  
|[CEdit::SetSel](#setsel)|Выбирает диапазон символов в элемент управления редактированием.|  
|[CEdit::SetTabStops](#settabstops)|Задает позиции табуляции в многострочного поля ввода.|  
|[CEdit::ShowBalloonTip](#showballoontip)|Отображает всплывающую подсказку, связанной с текущего элемента управления edit.|  
|[CEdit::Undo](#undo)|Отменяет последнюю операцию редактирования управления.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления редактированием является прямоугольная дочернее окно, в котором пользователь может ввести текст.  
  
 Элемент управления редактированием можно создать на основе шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CEdit` для создания `CEdit` объекта, а затем вызвать [создать](#create) функция-член для создания окна элемента управления edit и присоединить его к `CEdit` объекта.  
  
 Построение может быть задачей в классе, производном от `CEdit`. Создание конструктора для производного класса и вызове **создать** из внутри конструктора.  
  
 `CEdit`наследует важные функции из `CWnd`. Чтобы задать и получить текст из `CEdit` , используйте `CWnd` функции-члены [SetWindowText](cwnd-class.md#setwindowtext) и [GetWindowText](cwnd-class.md#getwindowtext), какие set или get изменения все содержимое элемента управления, даже если он Представляет элемент управления многострочным. Строки текста в многострочном элементе управления разделенных последовательностями символов «\r\n». Кроме того, если элемент управления редактирования содержит несколько строк, get и set часть текста элемента управления путем вызова `CEdit` функции-члены [GetLine](#getline), [SetSel](#setsel), [GetSel](#getsel)и [ ReplaceSel](#replacesel).  
  
 Если вы хотите обработки сообщений Windows уведомления, отправленные элемент управления редактированием с родительским (обычно класс, производный от `CDialog`), добавить схему сообщений входа и обработчик сообщений функции-члена родительского класса для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 **ON_**уведомления **(** *идентификатор, memberFxn***)**  
  
 где `id` указывает идентификатор дочернего окна элемента управления, отправляющего уведомление, и `memberFxn` имя функции-члена родительского вы написали для обработки уведомления.  
  
 Прототип функции родительского элемента выглядит следующим образом:  
  
 **afx_msg** void memberFxn **();**  
  
 Ниже приведен список возможных операций схемы сообщений и описание вариантов, в которых они были бы отправлены на родительский:  
  
- **ON_EN_CHANGE** смены действие, которое может изменен текст в элементе управления. В отличие от **EN_UPDATE** , это уведомление отправляется уведомление после отображения обновлений Windows.  
  
- **ON_EN_ERRSPACE** поле редактирования не удается выделить достаточно памяти для выполнения конкретного запроса.  
  
- **ON_EN_HSCROLL** пользователь щелкает элемент управления редактирования горизонтальную полосу прокрутки. Родительское окно получает уведомление до обновления экрана.  
  
- **ON_EN_KILLFOCUS** поле редактирования теряет фокус ввода.  
  
- **ON_EN_MAXTEXT** текущий курсор превысил указанное число символов для элемента управления редактирования и было усечено. Также отправляется, когда элемент управления редактированием не имеет **ES_AUTOHSCROLL** стиль и количество символов для вставки превышает ширину элемента управления. Также отправляется, когда элемент управления редактированием не имеет **ES_AUTOVSCROLL** стиль и общее число строк, возникающие в результате вставки текста превысит высоту элемента управления.  
  
- **ON_EN_SETFOCUS** отправляется, когда элемент управления редактированием получает фокус ввода.  
  
- **ON_EN_UPDATE** управления правка собирается отобразить измененный текст. Отправлено после форматирования текста элемента управления, но до его блокировки текст, чтобы размер окна может быть изменен, при необходимости.  
  
- **ON_EN_VSCROLL** пользователь щелкает элемент управления редактированием вертикальной полосы прокрутки. Родительское окно получает уведомление до обновления экрана.  
  
 Если вы создаете `CEdit` объекта в диалоговом окне, `CEdit` объект автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CEdit` из ресурса диалогового окна с помощью редактора диалоговых окон, `CEdit` объект автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CEdit` объекта в окне, может потребоваться удалить его. Если вы создаете `CEdit` объекта в стеке, удаляется автоматически. При создании `CEdit` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь закроет Windows изменение элемента управления. Если выделять память в `CEdit` объекта, переопределите `CEdit` деструктор для удаления распределения.  
  
 Чтобы изменить стили, определенные в элемент управления редактированием (такие как **ES_READONLY**) вы должны отправить определенных сообщений в элемент управления, вместо использования [ModifyStyle](cwnd-class.md#modifystyle). В разделе [изменение стилей элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775464) в Windows SDK.  
  
 Дополнительные сведения о `CEdit`, см.:  
  
- [Элементы управления](../../mfc/controls-mfc.md)  
  
-   Статья базы знаний Q259949: INFO: SetCaretPos() — не соответствует с CEdit или элементами управления CRichEditCtrl  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="canundo"></a>CEdit::CanUndo  
 Вызывайте эту функцию, чтобы определить, можно ли отменить последнюю операцию редактирования.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если последнюю операцию редактирования можно сделать с помощью вызова **отменить** функции-члена; 0, если оно не может быть отменено.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::Undo](#undo).  
  
##  <a name="cedit"></a>CEdit::CEdit  
 Создает объект `CEdit`.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [создать](#create) для создания окна редактирования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>CEdit::CharFromPos  
 Эта функция вызывается для получения отсчитываемый от нуля и индексы символ знака ближайшего указанную точку в это `CEdit` управления  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Координаты точки в клиентской области данного объекта `CEdit` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс символа в низкого порядка **WORD**и индекс строки в высокого порядка **WORD**.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Эта функция-член — доступны, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>CEdit::Clear  
 Эта функция вызывается для удаления (clear) текущее выделение (если таковые имеются) в элементе управления.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Удаления, выполняемые **снимите** можно сделать, вызвав [отменить](#undo) функции-члена.  
  
 Чтобы удалить текущее выделение и поместить удаленные содержимое в буфер обмена, вызовите [Вырезать](#cut) функции-члена.  
  
 Дополнительные сведения см. в разделе [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>CEdit::Copy  
 Эта функция вызывается для копирование текущее выделение (если таковые имеются) в поле редактирования в буфер обмена в **CF_TEXT** формат.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>CEdit::Create  
 Создает элемент управления редактирования Windows и прикрепляет его к `CEdit` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Указывает стиль редактирования элемента управления. Примените любое сочетание [изменение стилей](edit-styles.md) к элементу управления.  
  
 `rect`  
 Задает размер и положение элемента управления edit. Может быть `CRect` объекта или `RECT` структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления редактирования (обычно `CDialog`). Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления edit.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CEdit` объекта в два этапа. Во-первых, вызовите `CEdit` конструктора, а затем вызовите метод **создать**, который создает управления редактированием Windows и прикрепляет его к `CEdit` объекта.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), и [WM_ GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) сообщений в поле редактирования.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), и [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CEdit`, добавить схему сообщений к новому классу и переопределить выше функции-члены обработчика сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Применить следующие [стили окна](window-styles.md) для элемента управления.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_GROUP** для группировки элементов управления  
  
- **WS_TABSTOP** включать управления редактированием в порядке табуляции  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>CEdit::Cut  
 Эта функция вызывается для удаления (вырезание) текущее выделение (если таковые имеются) в элементе управления и скопируйте удаляемый текст в буфер обмена в **CF_TEXT** формат.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Примечания  
 Удаление выполненных **Вырезать** можно сделать, вызвав [отменить](#undo) функции-члена.  
  
 Чтобы удалить выбранные элементы без помещения удаляемый текст в буфер обмена, вызовите [снимите](#clear) функции-члена.  
  
 Дополнительные сведения см. в разделе [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>CEdit::EmptyUndoBuffer  
 Эта функция вызывается для сброса (clear) флаг отмены элемента управления edit.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Примечания  
 Элемент управления для редактирования будет невозможно отменить последнюю операцию. Флаг отмены устанавливается каждый раз, когда на операцию в поле редактирования, можно отменить.  
  
 Флаг отмены будет автоматически очищен каждый раз, когда [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) или [метод SetHandle](#sethandle) `CWnd` функции-члены вызываются.  
  
 Дополнительные сведения см. в разделе [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>CEdit::FmtLines  
 Вызовите эту функцию для задания включения мягкого разрыва строки символов или отключить в элементе управления редактирования несколько строк.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>Параметры  
 *bAddEOL*  
 Указывает, должны быть вставлены мягкого разрыва строки символов. Значение **TRUE** вставляет символы; значение **FALSE** удаляет их.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все форматирование будет выполняться; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Мягкий перенос состоит из двух символы возврата каретки и перевода строки, вставленной в конце строки, разорвано из-за перенос слов. Разрыв строки жесткого состоит из одного символы возврата каретки и перевода строки. Не подвержены строках, оканчивающихся разрыв строки жесткого `FmtLines`.  
  
 Windows будет отвечать только в том случае, если `CEdit` объект — это элемент управления многострочного редактирования.  
  
 `FmtLines`влияет только на буфер, возвращенный при [GetHandle](#gethandle) и текст, возвращенный [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627). Он не оказывает влияния на отображение текста в поле редактирования.  
  
 Дополнительные сведения см. в разделе [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>CEdit::GetCueBanner  
 Получает текст, отображаемый в качестве текст подсказки, то подсказки в элемент управления редактирования, если элемент управления будет пустым.  
  
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
  
 Для второй перегрузке [CString](../../atl-mfc-shared/using-cstring.md) , содержащий текст подсказки, если метод выполнен успешно; в противном случае — пустая строка (»»).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) сообщение, которое описано в Windows SDK. Дополнительные сведения см. в разделе [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) макрос.  
  
##  <a name="getfirstvisibleline"></a>CEdit::GetFirstVisibleLine  
 Эта функция вызывается для определения верхнего видимой строки в элемент управления редактированием.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс верхнего видимой строкой. Однострочный элементах управления для редактирования возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>CEdit::GetHandle  
 Эта функция вызывается для получения дескриптора для памяти, выделенной для элемента управления редактирования несколько строк.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор локальной памяти, который идентифицирует буфер, содержащий содержимое элемента управления. Если возникает ошибка, например отправлять сообщение в элемент управления редактирования однострочный, возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор является дескриптором локальной памяти и могут быть использованы по любому **локального** функции памяти Windows, которые принимают локальной памяти обрабатывать как параметр.  
  
 **GetHandle** обрабатывается только элементы управления редактирования несколько строк.  
  
 Вызовите **GetHandle** для элемента управления редактирования несколько строк в диалоговом окне только в том случае, если диалоговое окно было создано в **DS_LOCALEDIT** стиля флаг. Если **DS_LOCALEDIT** стиль не задан, будут по-прежнему получить ненулевое возвращаемое значение, но вы не сможете использовать возвращаемое значение.  
  
> [!NOTE]
> **GetHandle** не будет работать с Windows 95/98. При вызове метода **GetHandle** в Windows 95/98 вернет **NULL**. **GetHandle** будет работать, как описано в Windows NT 3.51 и более поздних версиях.  
  
 Дополнительные сведения см. в разделе [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>CEdit::GetHighlight  
 Возвращает индексы первый и последний символ в диапазоне, выделенного в текущий элемент управления редактирования текста.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[выходной] `pichStart`|Отсчитываемый от нуля индекс первого символа в диапазоне от текста, который будет выделен.|  
|[выходной] `pichEnd`|Отсчитываемый от нуля индекс последнего символа в диапазоне от текста, который будет выделен.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) сообщение, которое описано в Windows SDK.  
  
##  <a name="getlimittext"></a>CEdit::GetLimitText  
 Вызовите эту функцию-член для получения текста предел для данного `CEdit` объекта.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий текст предельный размер в байтах для данного `CEdit` объекта.  
  
### <a name="remarks"></a>Примечания  
 Ограничение текста — максимальный объем текста, в байтах, который может принимать элемент управления для редактирования.  
  
> [!NOTE]
>  Эта функция-член — доступны, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
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
 Указывает номер строки для извлечения из многострочного элемента управления edit. Номера строк отсчитываются от нуля; значение 0 задает первую строку. Этот параметр учитывается элементом управления редактирования одной строки.  
  
 `lpszBuffer`  
 Указатель на буфер, который получает копию строки. Первое слово буфера необходимо указать максимальное число символов, которые могут быть скопированы в буфер.  
  
 `nMaxLength`  
 Указывает максимальное число байтов, которые могут быть скопированы в буфер. `GetLine`помещает это значение в первом слове `lpszBuffer` перед вызовом в Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число фактически скопированных байтов. Возвращаемое значение равно 0, если номер строки, заданный параметром `nIndex` больше, чем число строк в элементе управления.  
  
### <a name="remarks"></a>Примечания  
 Скопированной строке не содержит знак завершения null.  
  
 Дополнительные сведения см. в разделе [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>CEdit::GetLineCount  
 Вызывайте эту функцию для извлечения нескольких строк в элементе управления edit несколько строк.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поля ввода integer, содержащее количество строк в несколько строк. Если текст не был введен в элемент управления, возвращаемое значение — 1.  
  
### <a name="remarks"></a>Примечания  
 `GetLineCount`только обрабатывается в элементах управления для редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>CEdit::GetMargins  
 Вызовите эту функцию-член для извлечения левого и правого полей поля ввода.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина левого поля в низкого порядка **WORD** и ширину правого поля высокого порядка **WORD**.  
  
### <a name="remarks"></a>Примечания  
 Поля измеряются в пикселях.  
  
> [!NOTE]
>  Эта функция-член — доступны, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="getmodify"></a>CEdit::GetModify  
 Вызывайте эту функцию, чтобы определить, были ли изменены содержимое элемента управления edit.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если содержимое элемента управления редактирования были изменены; 0, если они остаются без изменений.  
  
### <a name="remarks"></a>Примечания  
 Windows поддерживает внутреннего флага, показывающее, были ли изменены содержимое элемента управления. Этот флаг очищается, когда создается элемент управления для редактирования и также могут быть удалены путем вызова [SetModify](#setmodify) функции-члена.  
  
 Дополнительные сведения см. в разделе [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>CEdit::GetPasswordChar  
 Эта функция вызывается для получения символ пароля, который отображается в элемент управления редактированием при вводе текста.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает символ, который будет отображаться вместо символа, который пользователь введет. Возвращает значение `NULL` Если знака пароль не существует.  
  
### <a name="remarks"></a>Примечания  
 При создании элемента управления Правка с **ES_PASSWORD** стиль, библиотеки DLL, которая поддерживает элемент управления определяет знак пароля по умолчанию. Манифест или [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) метод определяет, какие библиотеки DLL поддерживает элемент управления для редактирования. Если user32.dll поддерживает элемент управления для редактирования, знак пароля по умолчанию — звездочка ("*", U + 002A). Если comctl32.dll версии 6 поддерживает элемент управления для редактирования, символ по умолчанию — ЧЕРНЫЙ КРУГ («●», U + 25CF). Дополнительные сведения о поддерживающий DLL и версии общие элементы управления в разделе [оболочка и версии общих элементов управления](http://msdn.microsoft.com/library/windows/desktop/bb776779).  
  
 Этот метод отправляет [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>CEdit::GetRect  
 Эта функция вызывается для получения прямоугольника форматирования элемента управления edit.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает `RECT` структуру, которая получает прямоугольника форматирования.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольника форматирования является ограничивающим прямоугольником текста, которая не зависит от размера окна элемента управления edit.  
  
 Прямоугольника форматирования элемента управления редактированием несколько строк могут быть изменены [SetRect](#setrect) и [SetRectNP](#setrectnp) функции-члены.  
  
 Дополнительные сведения см. в разделе [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::LimitText](#limittext).  
  
##  <a name="getsel"></a>CEdit::GetSel  
 Вызовите эту функцию для получения начального и конечного позиций символов в текущем выделенном фрагменте (если таковые имеются) элемент управления, с помощью возвращаемого значения или параметры.  
  
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
 Ссылка на целое число, будут получать позицию первого символа невыбранные за пределами текущего выделенного фрагмента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Версию, которая возвращает `DWORD` возвращает значение, содержащее начальную позицию в младшее слово и позицию первого символа невыбранные после окончания выделенного текста в word высокого порядка.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>CEdit::HideBalloonTip  
 Скрывает любой всплывающей подсказке, связанной с текущего элемента управления edit.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция отправляет [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) сообщение, которое описано в Windows SDK.  
  
##  <a name="limittext"></a>CEdit::LimitText  
 Вызывайте эту функцию, чтобы ограничить длину текста, который пользователь может ввести в элемент управления.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nChars`  
 Указывает длину (в байтах), пользователь может ввести текст. Если этот параметр равен 0, значение длины текста **UINT_MAX** байт. Это поведение установлено по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Изменение текста ограничения ограничивает только текст, который пользователь может ввести. Он уже не влияет на любой текст в элементе управления, и не влияет на длину текста, копируются в поле редактирования по [SetWindowText](cwnd-class.md#setwindowtext) функции-члена `CWnd`. Если приложение использует `SetWindowText` поместить текст в элемент управления редактированием, чем указано в вызове функции `LimitText`, пользователь может удалять любой текст в поле редактирования. Тем не менее предел текст помешает пользователю заменить существующий текст новым текстом, если удаление выделенного вызывает текста падают ниже предельного количества текста.  
  
> [!NOTE]
>  В Win32 (Windows NT и Windows 95/98) [SetLimitText](#setlimittext) заменяет эту функцию.  
  
 Дополнительные сведения см. в разделе [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>CEdit::LineFromChar  
 Вызывайте эту функцию, чтобы получить номер строки в строку, содержащую символ с указанным индексом.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс значение для требуемого символа в тексте элемента управления, или значение -1. Если `nIndex` равно -1, он задает текущую строку, то есть строки, содержащей курсор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля номер строки, содержащей индекс символа, заданный `nIndex`. Если `nIndex` равно -1, возвращается число строк, содержащий первый символ выделения. Если не выбрано, возвращается текущий номер строки.  
  
### <a name="remarks"></a>Примечания  
 Индекс символа — количество символов с начала элемента управления.  
  
 Эта функция-член используется только элементами управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>CEdit::LineIndex  
 Эта функция вызывается для получения индекс символа строки внутри многострочного редактирования элемента управления.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nLine`  
 Содержит значение индекса для нужной строке в тексте элемента управления, или значение -1. Если `nLine` равно -1, он задает текущую строку, то есть строки, содержащей курсор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс строки, указанной в `nLine` или -1, если указанный номер строки больше, чем число строк в элементе управления.  
  
### <a name="remarks"></a>Примечания  
 Индекс символа — количество символов с начала элемента управления редактированием на указанную строку.  
  
 Эта функция-член обрабатывается только элементы управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
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
  
 Для многострочных полей редактирования, возвращаемое значение — это длина в `TCHAR`s линии определяется `nLine` параметра. Для [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] текст, длина число байтов в строке, а для текст в кодировке Юникод, длина число символов в строке. Длина не включает символ возврата каретки в конце строки.  
  
 Если `nLine` параметр больше, чем количество символов в элементе управления, возвращаемое значение равно нулю.  
  
 Если `nLine` параметра равно -1, возвращаемое число невыбранные знаков в строки, содержащие выбранные символы. Например если выбор распространяется с четвертого символа одну строку восьмой символа в конце следующей строки, возвращаемое значение равно 10. То есть три символов в первой строке и семь на следующей.  
  
 Дополнительные сведения о `TCHAR` введите см. в разделе `TCHAR` строки в таблице в [типы данных Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживается [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>CEdit::LineScroll  
 Эта функция вызывается для прокрутки элемента управления редактированием несколько строк текста.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nLines`  
 Указывает количество строк для прокрутки по вертикали.  
  
 `nChars`  
 Указывает количество позиций знаков для прокрутки по горизонтали. Это значение игнорируется, если для редактирования элемента управления либо **ES_RIGHT** или **ES_CENTER** стиля.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Поле редактирования не вертикальную прокрутку, после последней строки текста в элементе управления. Если строка текущего плюс количество строк, определяемое `nLines` превышает общее число строк в элементе управления, значение корректируется, чтобы последняя строка элемента управления может прокручиваться в верхней части окна элемента управления edit.  
  
 `LineScroll`используется для прокрутки по горизонтали за последним символом любой строки.  
  
 Дополнительные сведения см. в разделе [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>CEdit::Paste  
 Эта функция вызывается для вставки данных из буфера обмена в `CEdit` в позиции курсора.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Примечания  
 Вставляются данные только в том случае, если в буфере обмена содержатся данные в **CF_TEXT** формат.  
  
 Дополнительные сведения см. в разделе [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>CEdit::PosFromChar  
 Эта функция вызывается для получения позиции (в левом верхнем углу) определенный символ в рамках этого `CEdit` объекта.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Отсчитываемый от нуля индекс заданного символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Координаты левого верхнего угла символ `nChar`.  
  
### <a name="remarks"></a>Примечания  
 Символ, указанный его индекс, отсчитываемый от нуля значение. Если `nChar` больше индекса последнего символа в этом `CEdit` объекта, возвращаемое значение указывает координаты позиции символа сразу после последнего символа в данном `CEdit` объекта.  
  
> [!NOTE]
>  Эта функция-член — доступны, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::LineFromChar](#linefromchar).  
  
##  <a name="replacesel"></a>CEdit::ReplaceSel  
 Вызывайте эту функцию, чтобы заменить текущее выделение в элемент управления редактированием текст, заданный параметром `lpszNewText`.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszNewText`  
 Указывает нулем строка, содержащая текст для замены.  
  
 `bCanUndo`  
 Чтобы указать, что эту функцию можно отменить, задайте значение для этого параметра значение **TRUE** . Значение по умолчанию — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Заменяет часть текста в элементе управления редактирования. Если вы хотите заменить весь текст, используйте [CWnd::SetWindowText](cwnd-class.md#setwindowtext) функции-члена.  
  
 Если выделенный фрагмент отсутствует, текст замены вставляется в текущем положении курсора.  
  
 Дополнительные сведения см. в разделе [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::LineIndex](#lineindex).  
  
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
 Если `false`, баннер подсказки не выводится, когда пользователь щелкает в поле редактирования и передает фокус на элемент управления.  
  
 Если `true`, рисуется баннер подсказки, даже в том случае, если элемент управления имеет фокус. Баннер подсказки исчезает, когда пользователь начинает вводить в элементе управления.  
  
 Значение по умолчанию — `false`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) сообщение, которое описано в Windows SDK. Дополнительные сведения см. в разделе [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) макрос.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется [CEdit::SetCueBanner](#setcuebanner) метод.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>CEdit::SetHandle  
 Вызовите эту функцию для задания дескриптор к локальной памяти, используемого элементом управления редактирования несколько строк.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>Параметры  
 *hBuffer*  
 Содержит дескриптор к локальной памяти. Этот дескриптор должен быть создан предыдущим вызовом [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows с помощью функции **LMEM_MOVEABLE** флаг. Предполагается, что память содержать строку, завершающуюся значением null. Если это не так, первый байт выделенной памяти должен быть равным 0.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления для редактирования будет использовать этот буфер для хранения текста, отображаемого вместо выделения буфера свой собственный.  
  
 Эта функция-член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Прежде чем приложение задает новый дескриптор памяти, следует использовать [GetHandle](#gethandle) получить дескриптор текущий буфер памяти и освобождения памяти используется, что и функция-член **LocalFree** функции Windows.  
  
 `SetHandle`Очищает буфер отмены ( [CanUndo](#canundo) функция-член возвращает 0) и флаг внутреннего изменения ( [GetModify](#getmodify) функция-член возвращает 0). Перерисовывается окна элемента управления edit.  
  
 Можно использовать эту функцию-член в элементе управления edit несколько строк в диалоговом окне только в том случае, если вы создали диалогового окна с **DS_LOCALEDIT** стиля флаг.  
  
> [!NOTE]
> **GetHandle** не будет работать с Windows 95/98. При вызове метода **GetHandle** в Windows 95/98 вернет **NULL**. **GetHandle** будет работать, как описано в Windows NT 3.51 и более поздних версиях.  
  
 Дополнительные сведения см. в разделе [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), и [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>CEdit::SetHighlight  
 Выделяет текст, отображаемый в текущий диапазон поля ввода.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `ichStart`|Отсчитываемый от нуля индекс первого символа в диапазоне текста для выделения.|  
|[in] `ichEnd`|Отсчитываемый от нуля индекс последнего символа в диапазоне текста для выделения.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) сообщение, которое описано в Windows SDK.  
  
##  <a name="setlimittext"></a>CEdit::SetLimitText  
 Вызовите эту функцию-член ограничение текст для этого `CEdit` объекта.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `nMax`  
 Новый предел текст в символах.  
  
### <a name="remarks"></a>Примечания  
 Ограничение текста — максимальный объем текста, в символы, которые может принимать элемент управления для редактирования.  
  
 Изменение текста ограничения ограничивает только текст, который пользователь может ввести. Он уже не влияет на любой текст в элементе управления, и не влияет на длину текста, копируются в поле редактирования по [SetWindowText](cwnd-class.md#setwindowtext) функции-члена `CWnd`. Если приложение использует `SetWindowText` поместить текст в элемент управления редактированием, чем указано в вызове функции `LimitText`, пользователь может удалять любой текст в поле редактирования. Тем не менее предел текст помешает пользователю заменить существующий текст новым текстом, если удаление выделенного вызывает текста падают ниже предельного количества текста.  
  
 Эта функция заменяет [LimitText](#limittext) в Win32.  
  
 Дополнительные сведения см. в разделе [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmargins"></a>CEdit::SetMargins  
 Этот метод используется для задания левого и правого полей поля ввода.  
  
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
>  Эта функция-член — доступны, начиная с Windows 95 и Windows NT 4.0.  
  
 Дополнительные сведения см. в разделе [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmodify"></a>CEdit::SetModify  
 Эта функция вызывается для установки или снятия измененного флага для элемента управления.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Значение **TRUE** указывает, что текст был изменен и значение **FALSE** указывает, он не изменяется. По умолчанию имеет значение измененного флага.  
  
### <a name="remarks"></a>Примечания  
 Измененный флаг указывает, был изменен ли текст в поле редактирования. Автоматически устанавливается каждый раз, когда пользователь изменяет текст. Значения могут быть получены с [GetModify](#getmodify) функции-члена.  
  
 Дополнительные сведения см. в разделе [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::GetModify](#getmodify).  
  
##  <a name="setpasswordchar"></a>CEdit::SetPasswordChar  
 Эта функция вызывается для установки и удаления символ пароля, отображаемых в элементе управления редактирования при вводе текста.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>Параметры  
 *CH*  
 Указывает символ для отображения вместо знак, введенный пользователем. Если *ch* равно 0, отображаются фактические символы, введенный пользователем.  
  
### <a name="remarks"></a>Примечания  
 Если задан символ пароля, этим символом отображается для каждого символьные типы пользователей.  
  
 Эта функция-член не оказывает влияния на несколько строк элемента управления edit.  
  
 Когда `SetPasswordChar` вызове функции-члена `CEdit` будет перерисовывает все символы видимой, используя символ, указанный *ch*.  
  
 Если элемент управления для редактирования создается с [ES_PASSWORD](edit-styles.md) , знак пароля по умолчанию задан стиль звездочку (  **\*** ). Этот стиль удаляется, если `SetPasswordChar` вызывается с *ch* присвоено значение 0.  
  
 Дополнительные сведения см. в разделе [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>CEdit::SetReadOnly  
 Вызывает эту функцию для задания состояния только для чтения элемента управления edit.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bReadOnly`  
 Указывает, следует ли установка или удаление состояния только для чтения поле редактирования. Значение **TRUE** задает состояние только для чтения; значение **FALSE** задает состояние для чтения и записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно, или 0, если ошибка возникает.  
  
### <a name="remarks"></a>Примечания  
 Текущее значение параметра можно найти с помощью тестирования [ES_READONLY](edit-styles.md) флаг в значение, возвращаемое [CWnd::GetStyle](cwnd-class.md#getstyle).  
  
 Дополнительные сведения см. в разделе [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>CEdit::SetRect  
 Вызывайте эту функцию, чтобы изменить размеры прямоугольника с помощью по указанным координатам.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает на `RECT` структуры или `CRect` , указывающий новые размеры прямоугольника форматирования.  
  
### <a name="remarks"></a>Примечания  
 Этот член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Используйте `SetRect` форматирования управления edit прямоугольник несколько строк. Прямоугольника форматирования является ограничивающим прямоугольником текста, которая не зависит от размера окна элемента управления edit. При создании элемента управления Правка прямоугольника форматирования совпадает со значением клиентской области окна элемента управления edit. С помощью `SetRect` функция-член, приложение может установить прямоугольника форматирования больше или меньше окна элемента управления edit.  
  
 Если полосы прокрутки для элемента управления edit, текст будет обрезан, не помещается в оболочку, если прямоугольника форматирования становится больше, чем окна. Если элемент управления редактирования содержит границы, прямоугольника форматирования уменьшается размер границы. Если настроить прямоугольнику, возвращенному `GetRect` функция-член, размер границы необходимо удалить, прежде чем передать прямоугольника для `SetRect`.  
  
 Когда `SetRect` вызывается элемент управления для редактирования в текст также переформатирован, повторно.  
  
 Дополнительные сведения см. в разделе [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>CEdit::SetRectNP  
 Вызовите эту функцию для задания прямоугольника форматирования элемента управления редактированием несколько строк.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает на `RECT` структуры или `CRect` объект, который указывает новый размеры прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольника форматирования является ограничивающим прямоугольником текста, которая не зависит от размера окна элемента управления edit.  
  
 `SetRectNP`идентичен `SetRect` функцию-член, за исключением того, что не перерисовке окна элемента управления edit.  
  
 При создании элемента управления Правка прямоугольника форматирования совпадает со значением клиентской области окна элемента управления edit. Путем вызова `SetRectNP` функция-член, приложение может установить прямоугольника форматирования больше или меньше окна элемента управления edit.  
  
 Если полосы прокрутки для элемента управления edit, текст будет обрезан, не помещается в оболочку, если прямоугольника форматирования становится больше, чем окна.  
  
 Этот член, обрабатывается только элементы управления редактирования несколько строк.  
  
 Дополнительные сведения см. в разделе [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::SetRect](#setrect).  
  
##  <a name="setsel"></a>CEdit::SetSel  
 Вызывайте эту функцию, чтобы выбрать диапазон символов в элемент управления редактированием.  
  
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
 Указывает начальную позицию в младшее слово и конечную позицию в word высокого порядка. Если младшее слово равен 0 и старшее слово — -1, выбирается весь текст в элементе управления. Если младшее слово равно -1, удаляется любое текущее выделение.  
  
 *bNoScroll*  
 Указывает, следует ли курсор прокручивания в представлении. Если **FALSE**, курсор в области просмотра. Если **TRUE**, курсор не в области просмотра.  
  
 `nStartChar`  
 Указывает начальную позицию. Если `nStartChar` равно 0 и `nEndChar` равно -1, все выбранные текст в элементе управления. Если `nStartChar` равно -1, удаляются все текущее выделение.  
  
 `nEndChar`  
 Указывает конечную позицию.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEdit::GetSel](#getsel).  
  
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
 Указывается массив целых чисел без знака, указав вкладке останавливается в диалоговых единицах. Единица размера диалогового окна является горизонтальное или вертикальное расстояние. Единицы диалогового окна горизонтальной равен одной четвертой текущий блок базовый ширины диалогового окна и 1 единица вертикальной диалогового окна равен одной восьмой текущий блок высота основы диалогового окна. Базовые единицы диалогового окна вычисляются в зависимости от высоты и ширины текущего системного шрифта. **GetDialogBaseUnits** Windows функция возвращает базовых единиц текущего диалогового окна в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если были заданы вкладок; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если текст копируется в элемент управления многострочного редактирования, любой символ табуляции в текстовом вызовет пространства для создаваемого до следующей позиции табуляции.  
  
 Чтобы установить позиции табуляции по умолчанию размер 32 единицы диалогового окна, вызовите конструктор версию эта функция-член. Чтобы установить позицию табуляции до размера, 32, вызовите версию с `cxEachStop` параметра. Чтобы установить позиции табуляции массив размеров, используйте версию с двумя параметрами.  
  
 Эта функция-член обрабатывается только элементы управления редактирования несколько строк.  
  
 `SetTabStops`не будут перерисовываться автоматически окна редактора. При изменении позиции табуляции для текста уже в элементе управления, вызовите [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) перерисовка окна редактора.  
  
 Дополнительные сведения см. в разделе [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) и [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CEditView::SetTabStops](ceditview-class.md#settabstops).  
  
##  <a name="showballoontip"></a>CEdit::ShowBalloonTip  
 Отображает всплывающую подсказку, связанной с текущего элемента управления edit.  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `pEditBalloonTip`|Указатель на [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) структура, описывающая всплывающей подсказки.|  
|[in] `lpszTitle`|Указатель на строку Юникода, содержащее заголовок окна всплывающей подсказки.|  
|[in] `lpszText`|Указатель на строку Юникода, содержащий текст подсказки.|  
|[in] `ttiIcon`|`INT` , Задающий тип значка, связываемый с всплывающей подсказки. Значение по умолчанию — `TTI_NONE`. Дополнительные сведения см. в разделе `ttiIcon` членом [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция отправляет [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) сообщение, которое описано в Windows SDK. Дополнительные сведения см. в разделе [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) макрос.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_cedit`, который используется для доступа к текущего элемента управления edit. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода отображает всплывающую подсказку для элемента управления. [CEdit::ShowBalloonTip](#showballoontip) метод задает текст заголовка и всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>CEdit::Undo  
 Эта функция вызывается для отмены последней операции управления для редактирования.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для элемента управления редактирования однострочный возвращаемое значение всегда равно ненулевое значение. Для элемента управления редактирования несколько строк, возвращается ненулевое значение, если операция отмены выполнена успешно, или 0, если происходит сбой операции отката.  
  
### <a name="remarks"></a>Примечания  
 Также можно отменить операцию отмены. Например, можно восстановить удаленный текст с первого вызова **отменить**. При условии, что нет промежуточных операции редактирования, можно удалить текст снова с помощью второго вызова **отменить**.  
  
 Дополнительные сведения см. в разделе [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
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
 [Класс CDialog](cdialog-class.md)
