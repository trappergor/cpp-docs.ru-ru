---
title: CEdit Class
ms.date: 09/12/2018
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
ms.openlocfilehash: 94769a6fb3c5fceefda96b54cebb35b0533a8afa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753216"
---
# <a name="cedit-class"></a>CEdit Class

Предоставляет функции элемента управления редактированием Windows.

## <a name="syntax"></a>Синтаксис

```
class CEdit : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CEdit::CEdit](#cedit)|Строит объект `CEdit` управления.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CEdit::CanUndo](#canundo)|Определяет, можно ли отменить операцию управления правки.|
|[CEdit::CharFromPos](#charfrompos)|Извлекает строку и индексы символов для символа, ближайшего к заданной позиции.|
|[CEdit::Ясно](#clear)|Удаляет (очищает) текущий выбор (если таковые) в элементе управления отсеиваний.|
|[CEdit::Copy](#copy)|Копирует текущий выбор (если таковой имеется) в элементе управления отсеивании в CF_TEXT формате.|
|[CEdit::Создание](#create)|Создает управление дейтом Windows и `CEdit` прикрепляет его к объекту.|
|[CEdit::Cut](#cut)|Удаляет (вырезает) текущий выбор (если таковой имеется) в элементе управления редактированием и копирует удаленный текст в CF_TEXT формате.|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Сброс (очищает) отменить флаг управления реитом.|
|[CEdit:FmtLines](#fmtlines)|Устанавливает включение мягких символов разрыва строки в элементе управления редактированием нескольких линий.|
|[CEdit:GetCueBanner](#getcuebanner)|Извлекает текст, отображаемый в виде текста, или наконечника, в элементаре управления, когда элемент управления пуст и не имеет фокусировки.|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Определяет наиболее видимую линию в элементаре управления реверсатом.|
|[CEdit::GetHandle](#gethandle)|Извлекает ручку в память, которая в настоящее время выделена для управления многолинейным элементом управления дейтом.|
|[CEdit::GetHighlight](#gethighlight)|Получает индексы исходных и заканчивающихся символов в диапазоне текста, который выделен в текущем элементе управления редактированием.|
|[CEdit:GetLimitText](#getlimittext)|Получает максимальное количество `CEdit` текста, которое это может содержать.|
|[CEdit::GetLine](#getline)|Извлекает строку текста из элемента управления редактированием.|
|[CEdit::GetLineCount](#getlinecount)|Извлекает количество строк в многолинейном элементе управления дейтом.|
|[CEdit::GetMargins](#getmargins)|Получает левый и правый `CEdit`края для этого .|
|[CEdit::GetModify](#getmodify)|Определяет, было ли изменено содержимое элемента управления отсеиваемым.|
|[CEdit::GetPasswordChar](#getpasswordchar)|Извлекает символ пароля, отображаемый в элементах управления редактированием при вводе текста пользователем.|
|[CEdit::GetRect](#getrect)|Получает форматирование прямоугольника управления правки.|
|[CEdit::GetSel](#getsel)|Получает первые и последние позиции символов текущего выбора в элементару редактирования.|
|[CEdit::HideBalloonTip](#hideballoontip)|Скрывает любой наконечник шарика, связанный с текущим управлением отсеивателя.|
|[CEdit::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в управление редактирования.|
|[CEdit::LineFromChar](#linefromchar)|Извлекает номер строки, содержащей указанный индекс символов.|
|[CEdit::LineIndex](#lineindex)|Извлекает индекс символов строки в элементе управления редактированием нескольких строк.|
|[CEdit::LineLength](#linelength)|Извлекает длину строки в элементуправления для отправления.|
|[CEdit::LineScroll](#linescroll)|Прокрутки текста многолинейного элемента управления редактированием.|
|[CEdit::Paste](#paste)|Вставляет данные из Clipboard в элемент управления правки в текущем положении курсора. Данные вставляются только в том случае, если Clipboard содержит данные в CF_TEXT формате.|
|[CEdit::PosFromChar](#posfromchar)|Извлекает координаты верхнего левого угла указанного индекса символов.|
|[CEdit::ReplaceSel](#replacesel)|Заменяет текущий выбор в элементару редактирования на указанный текст.|
|[CEdit::SetCueBanner](#setcuebanner)|Устанавливает текст, отображаемый в виде сигнала текста или наконечника, в элементаре управления, когда элемент управления пуст и не имеет фокусировки.|
|[CEdit::SetHandle](#sethandle)|Устанавливает ручку к локальной памяти, которая будет использоваться с помощью многолинейного элемента управления дейтом.|
|[CEdit::SetHighlight](#sethighlight)|Выделение диапазона текста, отображаемого в текущем элементе управления редактированием.|
|[CEdit::SetLimitText](#setlimittext)|Устанавливает максимальное количество `CEdit` текста, которое может содержаться.|
|[CEdit::SetMargins](#setmargins)|Устанавливает левый и правый `CEdit`края для этого .|
|[CEdit::SetModify](#setmodify)|Устанавливает или очищает флаг модификации для управления изменениями.|
|[CEdit::SetPasswordChar](#setpasswordchar)|Устанавливает или удаляет символ пароля, отображаемый в элементе управления редактированием при вводе текста пользователем.|
|[CEdit::SetReadOnly](#setreadonly)|Устанавливает только состояние элемента управления редактом только для чтения.|
|[CEdit::SetRect](#setrect)|Устанавливает прямоугольник форматирования многолинейного элемента управления правкой и обновляет элемент управления.|
|[CEdit::SetRectNP](#setrectnp)|Устанавливает прямоугольник форматирования многолинейного элемента управления правкой без перерисовки окна управления.|
|[CEdit::SetSel](#setsel)|Выбирает диапазон символов в элементауправления редактирования.|
|[CEdit::SetTabStops](#settabstops)|Устанавливает стопы вкладки в многолинейном элементе управления дейтом.|
|[CEdit::ShowBalloonTip](#showballoontip)|Отображает наконечник шара, связанный с текущим управлением отсеивателя.|
|[CEdit::Undo](#undo)|Обратный последний элемент управления изменением.|

## <a name="remarks"></a>Remarks

Элемент управления редактированием — это прямоугольное детское окно, в котором пользователь может вводить текст.

Вы можете создать элемент управления по правке либо из шаблона диалога, либо непосредственно в коде. В обоих случаях сначала `CEdit` позвоните `CEdit` в конструктор, чтобы построить объект, затем позвоните в `CEdit` функцию члена [Create,](#create) чтобы создать элемент управления дейтом Windows и прикрепить его к объекту.

Строительство может быть одноступенчатый процесс в `CEdit`классе, полученных из . Напишите конструктор для производного класса и позвоните `Create` изнутри конструктора.

`CEdit`наследует значительную `CWnd`функциональность от . Чтобы установить и извлечь `CEdit` текст из `CWnd` объекта, используйте функции участника [SetWindowText](cwnd-class.md#setwindowtext) и [GetWindowText,](cwnd-class.md#getwindowtext)которые устанавливают или получают все содержимое элемента управления редактированием, даже если это многолинейный элемент управления. Текстовые строки в многолиневом элементе управления разделены последовательностями символов ''r'n'. Кроме того, если элемент управления редактированием является многолинейным, получите `CEdit` и установите часть текста элемента управления, позвонив в функции участника [GetLine,](#getline) [SetSel,](#setsel) [GetSel](#getsel)и [ReplaceSel.](#replacesel)

Если вы хотите обрабатывать сообщения уведомлений Windows, отправленные элементом управления `CDialog`правкой, его родителю (обычно классу, полученному из), добавьте запись на карту сообщений и функцию обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись на карту сообщений принимает следующую форму:

  **ON_**_- ИДентификатор_**(id** _id_**,** _memberFxn)_ **)**

где `id` указывается идентификатор окна ребенка элементуправления `memberFxn` элемента управления, отправляющий уведомление, и имя функции родительского члена, написанной для обработки уведомления.

Прототип функции родителя:

**afx_msg** недействительным членfxn **( );**

Ниже приведен список потенциальных записей на карте сообщений и описание случаев, в которых они будут отправлены родителю:

- ON_EN_CHANGE Пользователь предпринял действие, которое могло изменить текст в элементе управления редактированием. В отличие от EN_UPDATE сообщения об уведомлении, это сообщение об уведомлении отправляется после обновления дисплея Windows.

- ON_EN_ERRSPACE Управление правкой не может выделить достаточно памяти для удовлетворения конкретного запроса.

- ON_EN_HSCROLL Пользователь нажимает горизонтальную панель прокрутки управления элементами отсечения. Родительское окно уведомляется перед обновлением экрана.

- ON_EN_KILLFOCUS Управление элемента милите теряет фокус ввода.

- ON_EN_MAXTEXT Текущая вставка превысила указанное количество символов для управления редактированием и была усечена. Также отправляется, когда элемент управления редактированием не имеет ES_AUTOHSCROLL стиле, а количество вставленных символов превышает ширину элемента управления редактированием. Также отправляется, когда элемент управления редактированием не имеет ES_AUTOVSCROLL стиля, а общее количество строк, возникающих в результате вставки текста, превышает высоту элемента управления редактированием.

- ON_EN_SETFOCUS Отправлено при элементировании элемента управления, получает фокус ввода.

- ON_EN_UPDATE Управление редактированием вот-вот отобразит измененный текст. Отправлено после того, как элемент управления отформатировал текст, но перед экраном — так, чтобы размер окна можно было изменить, если это необходимо.

- ON_EN_VSCROLL Пользователь нажимает на вертикальную панель прокрутки управления элементами отсечения. Родительское окно уведомляется перед обновлением экрана.

При создании `CEdit` объекта в диалоговом `CEdit` поле объект автоматически уничтожается при закрытии диалогового окна.

Если объект `CEdit` создается из ресурса диалогов с `CEdit` помощью редактора диалогов, объект автоматически уничтожается при закрытии диалогового окна.

Если вы `CEdit` создаете объект в окне, возможно, вам также придется уничтожить его. При создании `CEdit` объекта в стеке он уничтожается автоматически. Если объект `CEdit` создается на куче с помощью **новой** функции, необходимо **вызвать удаление** объекта, чтобы уничтожить его, когда пользователь прекратит управление отсеиванием Windows. Если вы выделяете `CEdit` какую-либо `CEdit` память в объекте, переопределить деструктор, чтобы избавиться от выделений.

Чтобы изменить определенные стили в элементару элемента управления (например, ES_READONLY), необходимо отправлять определенные сообщения в управление, а не использовать [ModifyStyle.](cwnd-class.md#modifystyle) Смотрите [стили управления отсеиваниями](/windows/win32/Controls/edit-control-styles) в SDK Windows.

Для получения `CEdit`дополнительной информации о, см. [Controls](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="ceditcanundo"></a><a name="canundo"></a>CEdit::CanUndo

Вызовите эту функцию, чтобы определить, можно ли отменить последнюю операцию по правке.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если последняя операция по правлению может `Undo` быть отменена вызовом к функции члена; 0, если это не может быть отменено.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации смотрите [EM_CANUNDO](/windows/win32/Controls/em-canundo) в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::Undo](#undo).

## <a name="ceditcedit"></a><a name="cedit"></a>CEdit::CEdit

Формирует объект `CEdit`.

```
CEdit();
```

### <a name="remarks"></a>Remarks

Используйте [Create](#create) для построения управления отсылки Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

## <a name="ceditcharfrompos"></a><a name="charfrompos"></a>CEdit::CharFromPos

Вызов ими функции для получения индексов нулевой линии и символов `CEdit` символа, ближайшего к указанной точке в этом элементе управления

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Координаты точки в клиентской `CEdit` области этого объекта.

### <a name="return-value"></a>Возвращаемое значение

Индекс символов в НИЗКОуровневом WORD и линейный индекс в высокоуровневом WORD.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Эта функция-член доступна начиная с Windows 95 и Windows NT 4.0.

Для получения дополнительной информации смотрите [EM_CHARFROMPOS](/windows/win32/Controls/em-charfrompos) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

## <a name="ceditclear"></a><a name="clear"></a>CEdit::Ясно

Вызовите эту функцию, чтобы удалить (очистить) текущий выбор (если таковые) в элементе управления отсеиваний.

```cpp
void Clear();
```

### <a name="remarks"></a>Remarks

Удаление, выполняемые `Clear` может быть отменено, позвонив в функцию участника [Undo.](#undo)

Чтобы удалить текущий выбор и поместить удаленное содержимое в Clipboard, позвоните в функцию участника [Cut.](#cut)

Для получения дополнительной информации смотрите [WM_CLEAR](/windows/win32/dataxchg/wm-clear) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

## <a name="ceditcopy"></a><a name="copy"></a>CEdit::Copy

Вызовите эту функцию, чтобы затмить текущий выбор (если таковой имеется) в элементе управления отсеивании в CF_TEXT формате.

```cpp
void Copy();
```

### <a name="remarks"></a>Remarks

Для получения дополнительной информации см. [WM_COPY](/windows/win32/dataxchg/wm-copy) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

## <a name="ceditcreate"></a><a name="create"></a>CEdit::Создание

Создает управление дейтом Windows и `CEdit` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления изменением. Примените к элементу управления любую комбинацию [стилей реприменения.](styles-used-by-mfc.md#edit-styles)

*rect*<br/>
Определяет размер и положение элемента управления отсечения. Может быть `CRect` объектом или `RECT` структурой.

*pParentWnd*<br/>
Определяет родительское окно элемента управления (обычно `CDialog`a). Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор элемента управления элемента мисеи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если инициализация является успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы строите `CEdit` объект в два этапа. Во-первых, `CEdit` вызов конструктора, а затем вызов `Create`, который создает `CEdit` управление windows отсваивательных и прикрепляет его к объекту.

При `Create` выполнении Windows отправляет [WM_NCCREATE,](/windows/win32/winmsg/wm-nccreate) [WM_NCCALCSIZE,](/windows/win32/winmsg/wm-nccalcsize) [WM_CREATE](/windows/win32/winmsg/wm-create)и [WM_GETMINMAXINFO](/windows/win32/winmsg/wm-getminmaxinfo) сообщения в управление отсеиваем.

Эти сообщения обрабатываются по умолчанию [onNcCreate,](cwnd-class.md#onnccreate) [OnNcCalcSize,](cwnd-class.md#onnccalcsize) [OnCreate](cwnd-class.md#oncreate)и [OnGetMinMaxInfo,](cwnd-class.md#ongetminmaxinfo) функционируют участники базового `CWnd` класса. Чтобы расширить обработку сообщений по `CEdit`умолчанию, вывемите класс из, добавьте карту сообщений в новый класс и переизбавьте вышеуказанные функции обработчика сообщений. Переопределить, `OnCreate`например, для выполнения необходимой инициализации для нового класса.

Примените следующие [стили окна](styles-used-by-mfc.md#window-styles) для управления отсеивание.

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

- WS_GROUP К управлению группой

- WS_TABSTOP Включить элементуправления отсвакой в порядок внесения табулентинга

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

## <a name="ceditcut"></a><a name="cut"></a>CEdit::Cut

Вызовите эту функцию, чтобы удалить (вырезать) текущий выбор (если таковой имеется) в элементе управления редактированием и скопировать удаленный текст в clipboard в CF_TEXT формате.

```cpp
void Cut();
```

### <a name="remarks"></a>Remarks

Удаление, выполняемые `Cut` может быть отменено, позвонив в функцию участника [Undo.](#undo)

Чтобы удалить текущий выбор без размещения удаленного текста в Clipboard, позвоните в функцию [участника Clear.](#clear)

Для получения дополнительной информации см. [WM_CUT](/windows/win32/dataxchg/wm-cut) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

## <a name="ceditemptyundobuffer"></a><a name="emptyundobuffer"></a>CEdit::EmptyUndoBuffer

Вызовите эту функцию для сбросить (очистить) отменить флаг управления редактировкой.

```cpp
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Remarks

Управление элементами отсечения теперь не сможет отменить последнюю операцию. Флаг отменить устанавливается всякий раз, когда операция в элементе управления правки должна быть отменена.

Флаг отменить автоматически очищается всякий раз, когда вызываются функции участника [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) или [SetHandle.](#sethandle) `CWnd`

Для получения дополнительной информации [EM_EMPTYUNDOBUFFER](/windows/win32/Controls/em-emptyundobuffer) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

## <a name="ceditfmtlines"></a><a name="fmtlines"></a>CEdit:FmtLines

Вызовите эту функцию, чтобы установить включение мягких символов, нарушаемых линиями, в рамках управления редактированием нескольких линий.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>Параметры

*bAddEOL*<br/>
Определяет, должны ли быть вставлены мягкие символы разрыва линии. Значение TRUE вставляет символы; значение FALSE удаляет их.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если происходит форматирование; в противном случае 0.

### <a name="remarks"></a>Remarks

Мягкий разрыв линии состоит из двух возвратов перевозки и линии корма вставляется в конце линии, которая нарушается из-за слова упаковки. Разрыв жесткой линии состоит из одного вагона возвращения и линии корма. Линии, которые заканчиваются с разрывом жесткой линии, не зависят от. `FmtLines`

Windows будет реагировать `CEdit` только в том случае, если объект является многолинейным элементом управления дейтом.

`FmtLines`только влияет на буфер, возвращенный [GetHandle](#gethandle) и текст, возвращенный [WM_GETTEXT.](/windows/win32/winmsg/wm-gettext) Это не влияет на отображение текста в элементе управления редактированием.

Для получения дополнительной информации см. [EM_FMTLINES](/windows/win32/Controls/em-fmtlines) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

## <a name="ceditgetcuebanner"></a><a name="getcuebanner"></a>CEdit:GetCueBanner

Извлекает текст, отображаемый в виде текста, или наконечника, в элементаре управления, когда элемент управления пуст.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
(ваут) Указатель на строку, содержащую текст сигнала.

*cchText*<br/>
(в) Количество символов, которые могут быть получены. Это число включает в себя термин NULL.

### <a name="return-value"></a>Возвращаемое значение

Для первой перегрузки, ПРАВДА, если метод является успешным; в противном случае FALSE.

Для второй перегрузки [CString,](../../atl-mfc-shared/using-cstring.md) содержащий текст сигнала, если метод успешен; в противном случае, пустая строка ("").

### <a name="remarks"></a>Remarks

Этот метод отправляет [EM_GETCUEBANNER](/windows/win32/Controls/em-getcuebanner) сообщение, которое описано в SDK Windows. Для получения дополнительной информации смотрите [Edit_GetCueBannerText](/windows/win32/api/commctrl/nf-commctrl-edit_getcuebannertext) макрос.

## <a name="ceditgetfirstvisibleline"></a><a name="getfirstvisibleline"></a>CEdit::GetFirstVisibleLine

Вызов исчерпнивайте эту функцию, чтобы определить наиболее видимую линию в элементе управления реверсатом.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс на нулевой основе верхней видимой линии. Для однострокаточного элемента управления элементами управления для элементов управления return значением 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации смотрите [EM_GETFIRSTVISIBLELINE](/windows/win32/Controls/em-getfirstvisibleline) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

## <a name="ceditgethandle"></a><a name="gethandle"></a>CEdit::GetHandle

Вызов ими функции для извлечения ручки в память, которая в настоящее время выделена для управления многолинейным элементом управления дейтом.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Локальная ручка памяти, идентифицирует буфер, удерживая содержимое элемента управления правкой. При возникновении ошибки, например отправки сообщения в элемент управления элементами детоирования одной строки, значение возврата составляет 0.

### <a name="remarks"></a>Remarks

Ручка является локальной ручкой памяти и может быть использована любой из **локальных** функций памяти Windows, которые принимают локальную ручку памяти в качестве параметра.

`GetHandle`обрабатывается только несколькими элементами управления элементами действенного элементов.

Вызов `GetHandle` для управления несколькими строками в диалоговом поле только в том случае, если диалоговый ящик был создан с набором флага DS_LOCALEDIT стилем. Если DS_LOCALEDIT стиль не установлен, вы все равно получите значение ненулевой доходности, но вы не сможете использовать возвращенное значение.

> [!NOTE]
> `GetHandle`не будет работать с Windows 95/98. Если вы `GetHandle` позвоните в Windows 95/98, он вернется NULL. `GetHandle`будет работать, как документально под Windows NT, версии 3.51 и позже.

Для получения дополнительной информации см. [EM_GETHANDLE](/windows/win32/Controls/em-gethandle) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

## <a name="ceditgethighlight"></a><a name="gethighlight"></a>CEdit::GetHighlight

Получает индексы первого и последнего символов в диапазоне текста, который выделен в текущем элементе управления редактированием.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pichStart*|(ваут) Нулевой индекс первого символа в выделенном диапазоне текста.|
|*pichEnd*|(ваут) Нулевой индекс последнего символа в выделенном диапазоне текста.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [EM_GETHILITE](/windows/win32/Controls/em-gethilite) сообщение, которое описано в SDK Windows. Оба `SetHighlight` `GetHighlight` и в настоящее время включены только для сборки UNICODE.

## <a name="ceditgetlimittext"></a><a name="getlimittext"></a>CEdit:GetLimitText

Вызовите эту функцию участника, `CEdit` чтобы получить ограничение текста для этого объекта.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий предел текста, в TCHARs, для этого `CEdit` объекта.

### <a name="remarks"></a>Remarks

Ограничение текста — это максимальное количество текста в TCHARs, которое может принять элемент управления редактированием.

> [!NOTE]
> Эта функция-член доступна начиная с Windows 95 и Windows NT 4.0.

Для получения дополнительной информации смотрите [EM_GETLIMITTEXT](/windows/win32/Controls/em-getlimittext) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

## <a name="ceditgetline"></a><a name="getline"></a>CEdit::GetLine

Вызов эту функцию, чтобы получить строку текста из управления редактирования и помещает его в *lpszBuffer*.

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

*Nindex*<br/>
Упоньте номер строки для извлечения из многолинейного элемента управления дейтом. Номера строк на нулевом уровне; значение 0 определяет первую строку. Этот параметр игнорируется однолинейным элементом управления дейтом.

*lpszBuffer*<br/>
Указывает на буфер, который получает копию строки. Первое слово буфера должно указывать максимальное количество TCHARs, которые могут быть скопированы в буфер.

*nMaxДлина*<br/>
Определяет максимальное количество символов TCHAR, которые могут быть скопированы в буфер. `GetLine`помещает это значение в первом слове *lpszBuffer* перед вызовом в Windows.

### <a name="return-value"></a>Возвращаемое значение

Число фактически скопированных символов. Значение возврата 0, если число строк, указанное *nIndex,* превышает количество строк в элементе управления рекретом.

### <a name="remarks"></a>Remarks

Скопированная строка не содержит символа с нулевым прекращением.

Для получения дополнительной информации см. [EM_GETLINE](/windows/win32/Controls/em-getline) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::GetLineCount](#getlinecount).

## <a name="ceditgetlinecount"></a><a name="getlinecount"></a>CEdit::GetLineCount

Вызов исчисляйте эту функцию, чтобы получить количество строк в многолинейном элементе управления дейтом.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целый ряд, содержащий количество строк в многолинейном элементе управления детона. Если текст не был введен в элемент управления редактирования, значение возврата составляет 1.

### <a name="remarks"></a>Remarks

`GetLineCount`обрабатывается только несколькими элементами управления элементами действенного элементов.

Для получения дополнительной информации [EM_GETLINECOUNT](/windows/win32/Controls/em-getlinecount) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

## <a name="ceditgetmargins"></a><a name="getmargins"></a>CEdit::GetMargins

Вызов эту функцию элемента для извлечения левой и правой краев этого элемента управления правки.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина левого края в МАЛОм заказе WORD и ширина правого края в высокоуровневом WORD.

### <a name="remarks"></a>Remarks

Поля измеряются в пикселях.

> [!NOTE]
> Эта функция-член доступна начиная с Windows 95 и Windows NT 4.0.

Для получения дополнительной информации [EM_GETMARGINS](/windows/win32/Controls/em-getmargins) см.

### <a name="example"></a>Пример

  Смотрите пример [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

## <a name="ceditgetmodify"></a><a name="getmodify"></a>CEdit::GetModify

Вызовите эту функцию, чтобы определить, было ли изменено содержимое элемента управления отсечения.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если содержимое управления отсечением было изменено; 0, если они остались неизменными.

### <a name="remarks"></a>Remarks

Windows поддерживает внутренний флаг, указывающий, было ли изменено содержимое элемента управления отсечением. Этот флаг очищается при первом создании элемента управления отсечения, а также может быть очищен, позвонив в функцию элемента [SetModify.](#setmodify)

Для получения дополнительной информации [EM_GETMODIFY](/windows/win32/Controls/em-getmodify) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

## <a name="ceditgetpasswordchar"></a><a name="getpasswordchar"></a>CEdit::GetPasswordChar

Вызов ими функции для получения символа пароля, отображаемого в элементах управления редактирования при вводе текста пользователем.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определяет символ, который будет отображаться, а не символ, набранный пользователем. Значение возврата NULL, если не существует символа пароля.

### <a name="remarks"></a>Remarks

При создании элемента управления редактированием со стилем ES_PASSWORD DLL, поддерживающий элемент управления, определяет символ пароля по умолчанию. Манифест или метод [InitCommonControlsEx](/windows/win32/api/commctrl/nf-commctrl-initcommoncontrolsex) определяет, какой DLL поддерживает управление ревердированным элементом. Если user32.dll поддерживает элемент управления редактированием, символом пароля по умолчанию является ASTERISK ('', U-002A). Если версия comctl32.dll 6 поддерживает элемент управления редактированием, символом по умолчанию является BLACK CIRCLE (', U'25CF). Для получения дополнительной информации о том, какие DLL и версия поддерживает общие [элементы](/previous-versions/windows/desktop/legacy/bb776779\(v=vs.85\))управления, см.

Этот метод отправляет [EM_GETPASSWORDCHAR](/windows/win32/Controls/em-getpasswordchar) сообщение, которое описано в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

## <a name="ceditgetrect"></a><a name="getrect"></a>CEdit::GetRect

Вызовите эту функцию, чтобы получить прямоугольник форматирования управления правки.

```cpp
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру, которая получает прямоугольник форматирования.

### <a name="remarks"></a>Remarks

Прямоугольник форматирования является ограничивающим прямоугольником текста, который не зависит от размера окна управления редактированием.

Форматирование прямоугольника многолинейного элемента управления правкой может быть изменено функциями членов [SetRect](#setrect) и [SetRectNP.](#setrectnp)

Для получения дополнительной информации смотрите [EM_GETRECT](/windows/win32/Controls/em-getrect) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::LimitText](#limittext).

## <a name="ceditgetsel"></a><a name="getsel"></a>CEdit::GetSel

Вызовите эту функцию, чтобы получить начальные и заканчивающиеся позиции символов текущего выбора (если таковые имеется) в элементаре управления редактированием, используя либо значение возврата, либо параметры.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>Параметры

*nStartChar*<br/>
Ссылка на бесселит, который получит позицию первого персонажа в текущем выборе.

*nEndChar*<br/>
Ссылка на бесседо, которая получит позицию первого невыбранного персонажа после окончания текущего выбора.

### <a name="return-value"></a>Возвращаемое значение

Версия, возвращающее DWORD, возвращает значение, содержащее исходное положение в слове с низким заказом, и положение первого невыбранного персонажа после окончания выбора в слове высокого порядка.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации см. [EM_GETSEL](/windows/win32/Controls/em-getsel) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

## <a name="cedithideballoontip"></a><a name="hideballoontip"></a>CEdit::HideBalloonTip

Скрывает любой наконечник шарика, связанный с текущим управлением отсеивателя.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Эта функция отправляет [EM_HIDEBALLOONTIP](/windows/win32/Controls/em-hideballoontip) сообщение, которое описано в SDK Windows.

## <a name="ceditlimittext"></a><a name="limittext"></a>CEdit::LimitText

Вызовите эту функцию, чтобы ограничить длину текста, который пользователь может ввести в управление редактирования.

```cpp
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>Параметры

*nChars*<br/>
Указать длину (в TCHARs) текста, который пользователь может ввести. Если этот параметр 0, длина текста устанавливается в UINT_MAX байтов. Это поведение по умолчанию.

### <a name="remarks"></a>Remarks

Изменение предела текста ограничивает только текст, в который может ввести пользователь. Он не влияет на любой текст, уже находящийся в элементе управления редактированием, и не влияет на `CWnd`длину текста, скопированного на элемент управления редактированием функцией члена [SetWindowText](cwnd-class.md#setwindowtext) в . Если приложение использует `SetWindowText` функцию для размещения большего количества текста в элемент `LimitText`управления редактированием, чем указано в вызове, пользователь может удалить любой текст в элементе управления редактирования. Однако ограничение текста не позволит пользователю заменить существующий текст новым текстом, если исключение текущего выбора не приведет к тому, что текст не будет ниже предела текста.

> [!NOTE]
> В Win32 (Windows NT и Windows 95/98) [SetLimitText](#setlimittext) заменяет эту функцию.

Для получения дополнительной информации смотрите [EM_LIMITTEXT](/windows/win32/Controls/em-limittext) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

## <a name="ceditlinefromchar"></a><a name="linefromchar"></a>CEdit::LineFromChar

Вызовите эту функцию, чтобы получить номер строки строки, содержащей указанный индекс символов.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Содержит значение индекса на нулевой основе для желаемого символа в тексте элемента управления редактированием или содержит -1. Если *nIndex* -1, он определяет текущую линию, то есть строку, содержащую карету.

### <a name="return-value"></a>Возвращаемое значение

Номер строки, основанной на нулевом уровне, содержащий индекс символов, указанный *nIndex.* Если *nIndex* -1, число строки, содержащей первый символ выбора, возвращается. Если нет выбора, текущий номер строки возвращается.

### <a name="remarks"></a>Remarks

Индекс символов — это количество символов с начала элемента управления редактирования.

Эта функция члена используется только с помощью многолинейного элемента управления действенной работы.

Для получения дополнительной информации см. [EM_LINEFROMCHAR](/windows/win32/Controls/em-linefromchar) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

## <a name="ceditlineindex"></a><a name="lineindex"></a>CEdit::LineIndex

Вызовите эту функцию, чтобы получить индекс символов строки в элементе управления редактирования нескольких строк.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>Параметры

*nЛиния*<br/>
Содержит значение индекса для нужной строки в тексте элемента управления редактированием или содержит -1. Если *nLine* -1, он определяет текущую линию, то есть линию, содержащую карету.

### <a name="return-value"></a>Возвращаемое значение

Индекс символов строки, указанный в *nLine* или -1, если указанное число строк превышает количество строк в элементе управления редактирования.

### <a name="remarks"></a>Remarks

Индекс символов — это количество символов от начала элемента управления редактированием до указанной строки.

Эта функция члена обрабатывается только несколькими элементами управления элементами действенности.

Для получения дополнительной информации см. [EM_LINEINDEX](/windows/win32/controls/em-lineindex) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

## <a name="ceditlinelength"></a><a name="linelength"></a>CEdit::LineLength

Извлекает длину строки в элементуправления для отправления.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>Параметры

*nЛиния*<br/>
Нулевой индекс символа в строке, длина которого должна быть извлечена. Значение по умолчанию — -1.

### <a name="return-value"></a>Возвращаемое значение

Для элементов управления редактированием одной строки значение возврата — это длина в TCHARs текста в элементаре редактирования.

Для многолинейных элементов управления элементами управления возврата значениевозврата — это длина в TCHARs линии, указанной параметром *nLine.* Для текста ANSI длина — это количество байтов в строке; для текста Unicode длина — это количество символов в строке. Длина не включает символ перевозки-возврата в конце линии.

Если параметр *nLine* превышает количество символов в элементе управления, значение возврата равно нулю.

Если параметр *nLine* -1, значение возврата — это число невыбранных символов в линиях, содержащих выбранные символы. Например, если выбор простирается от четвертого символа одной строки до восьмого символа с конца следующей строки, значение возврата составляет 10. То есть три символа на первой линии и семь на следующей.

Для получения дополнительной информации о типе TCHAR см. строку TCHAR в таблице в [типах данных Windows.](/windows/win32/WinProg/windows-data-types)

### <a name="remarks"></a>Remarks

Этот метод поддерживается [EM_LINELENGTH](/windows/win32/Controls/em-linelength) сообщением, которое описано в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::LineIndex](#lineindex).

## <a name="ceditlinescroll"></a><a name="linescroll"></a>CEdit::LineScroll

Вызовите эту функцию, чтобы прокрутить текст многолинейного элемента управления редактированием.

```cpp
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>Параметры

*nЛинии*<br/>
Определяет количество строк для прокрутки по вертикали.

*nChars*<br/>
Определяет количество позиций символов для прокрутки горизонтально. Это значение игнорируется, если элемент управления отсеивателя имеет стиль ES_RIGHT или ES_CENTER.

### <a name="remarks"></a>Remarks

Эта функция члена обрабатывается только несколькими элементами управления элементами действенности.

Элемент управления редактирования не прокручивается вертикально мимо последней строки текста в элементе управления редактирования. Если текущая строка плюс количество строк, указанных *nLines,* превышает общее количество строк в элементе управления отсеивании, значение корректируется таким образом, чтобы последняя строка элемента управления отсеиваю прокручивалась в верхней части окна управления отсеива.

`LineScroll`может быть использован для прокрутки горизонтально мимо последнего символа любой линии.

Для получения дополнительной информации см. [EM_LINESCROLL](/windows/win32/Controls/em-linescroll) в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::GetFirstVisibleLine](#getfirstvisibleline).

## <a name="ceditpaste"></a><a name="paste"></a>CEdit::Paste

Вызовите эту функцию, чтобы вставить данные из Clipboard в `CEdit` точку вставки.

```cpp
void Paste();
```

### <a name="remarks"></a>Remarks

Данные вставляются только в том случае, если Clipboard содержит данные в CF_TEXT формате.

Для получения дополнительной информации смотрите [WM_PASTE](/windows/win32/dataxchg/wm-paste) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

## <a name="ceditposfromchar"></a><a name="posfromchar"></a>CEdit::PosFromChar

Вызовите эту функцию, чтобы получить положение (верхний `CEdit` левый угол) данного символа в пределах этого объекта.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>Параметры

*Nchar*<br/>
Индекс нулевой основе указанного символа.

### <a name="return-value"></a>Возвращаемое значение

Координаты верхнего левого угла персонажа, указанного *nChar*.

### <a name="remarks"></a>Remarks

Символ определяется путем предоставления значения индекса с нулевым уровнем. Если *nChar* больше индекса последнего символа в этом `CEdit` объекте, значение возврата определяет координаты положения `CEdit` символа, только мимо последнего символа в этом объекте.

> [!NOTE]
> Эта функция-член доступна начиная с Windows 95 и Windows NT 4.0.

Для получения дополнительной информации см. [EM_POSFROMCHAR](/windows/win32/Controls/em-posfromchar) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::LineFromChar](#linefromchar).

## <a name="ceditreplacesel"></a><a name="replacesel"></a>CEdit::ReplaceSel

Вызовите эту функцию, чтобы заменить текущий выбор в элементару редактирования с текстом, указанным *lpszNewText.*

```cpp
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>Параметры

*lpszNewText*<br/>
Указывает на нулевую строку, содержащую текст замены.

*bCanUndo*<br/>
Чтобы указать, что эта функция может быть отменена, установите значение этого параметра на TRUE . Значение по умолчанию — FALSE.

### <a name="remarks"></a>Remarks

Заменяет только часть текста в элементе управления редактированием. Если вы хотите заменить весь текст, используйте функцию [cWnd::SetWindowText.](cwnd-class.md#setwindowtext)

Если нет текущего выбора, текст замены вставляется в текущем месте курсора.

Для получения дополнительной информации см. [EM_REPLACESEL](/windows/win32/Controls/em-replacesel) в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::LineIndex](#lineindex).

## <a name="ceditsetcuebanner"></a><a name="setcuebanner"></a>CEdit::SetCueBanner

Устанавливает текст, отображаемый в виде сигнала текста или наконечника, в элементаре управления, когда элемент управления пуст.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
(в) Указатель на строку, содержащую сигнал для отображения в элементе управления правкой.

*fDrawWhenFocused*<br/>
(в) Если FALSE, кий баннер не обращается, когда пользователь нажимает в элемент управления отсеивания и дает контроль фокус.

Если правда, кий баннер обращается даже тогда, когда элемент управления имеет фокус. Баннер кий исчезает, когда пользователь начинает вводить элемент управления.

Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [EM_SETCUEBANNER](/windows/win32/Controls/em-setcuebanner) сообщение, которое описано в SDK Windows. Для получения дополнительной информации см [Edit_SetCueBannerTextFocused.](/windows/win32/api/commctrl/nf-commctrl-edit_setcuebannertextfocused)

### <a name="example"></a>Пример

Следующий пример демонстрирует метод [CEdit::SetCueBanner.](#setcuebanner)

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

## <a name="ceditsethandle"></a><a name="sethandle"></a>CEdit::SetHandle

Вызов ими функции для установки ручки на локальную память, которая будет использоваться с помощью многолинейного элемента управления дейтом.

```cpp
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>Параметры

*hБуфер*<br/>
Содержит ручку в локальную память. Эта ручка должна быть создана предыдущим вызовом в функцию [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) Windows с помощью LMEM_MOVEABLE флага. Предполагается, что память содержит строку с нулевым завершением. Если это не так, первый байт выделенной памяти должен быть установлен на 0.

### <a name="remarks"></a>Remarks

Контроль редактирования будет использовать этот буфер для хранения отображаемого текста вместо выделения собственного буфера.

Эта функция члена обрабатывается только несколькими элементами управления элементами действенности.

Прежде чем приложение устанавливает новую ручку памяти, оно должно использовать функцию члена [GetHandle,](#gethandle) чтобы получить ручку в текущий буфер памяти и освободить эту память с помощью функции `LocalFree` Windows.

`SetHandle`очищает буфер отменить (функция члена [CanUndo](#canundo) затем возвращает 0) и внутренний флаг модификации (функция [GetModify,](#getmodify) затем возвращает 0). Окно управления отсечением перерисовывается.

Эту функцию члена можно использовать в многолинейном элементе управления дейтом в диалоговом поле только в том случае, если вы создали диалоговый ящик с набором флага DS_LOCALEDIT стилем.

> [!NOTE]
> `GetHandle`не будет работать с Windows 95/98. Если вы `GetHandle` позвоните в Windows 95/98, он вернется NULL. `GetHandle`будет работать, как документально под Windows NT, версии 3.51 и позже.

Для получения дополнительной информации, см [EM_SETHANDLE](/windows/win32/Controls/em-sethandle), [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc), и [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

## <a name="ceditsethighlight"></a><a name="sethighlight"></a>CEdit::SetHighlight

Выделение диапазона текста, отображаемого в текущем элементе управления редактированием.

```cpp
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ichStart*|(в) Нулевой индекс первого символа в диапазоне текста для выделения.|
|*ichEnd*|(в) Нулевой индекс последнего символа в диапазоне текста для выделения.|

### <a name="remarks"></a>Remarks

Этот метод отправляет [EM_SETHILITE](/windows/win32/Controls/em-sethilite) сообщение, которое описано в SDK Windows.  Этот метод отправляет [EM_SETHILITE](/windows/win32/Controls/em-sethilite) сообщение, которое описано в SDK Windows. Оба `SetHighlight` `GetHighlight` и включены только для сборки UNICODE.

## <a name="ceditsetlimittext"></a><a name="setlimittext"></a>CEdit::SetLimitText

Вызовите эту функцию участника, `CEdit` чтобы установить ограничение текста для этого объекта.

```cpp
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>Параметры

*nMax*<br/>
Новый текст предел, в символах.

### <a name="remarks"></a>Remarks

Ограничение текста — это максимальное количество текста в символах, которое может принять элемент управления редактированием.

Изменение предела текста ограничивает только текст, в который может ввести пользователь. Он не влияет на любой текст, уже находящийся в элементе управления редактированием, и не влияет на `CWnd`длину текста, скопированного на элемент управления редактированием функцией члена [SetWindowText](cwnd-class.md#setwindowtext) в . Если приложение использует `SetWindowText` функцию для размещения большего количества текста в элемент `LimitText`управления редактированием, чем указано в вызове, пользователь может удалить любой текст в элементе управления редактирования. Однако ограничение текста не позволит пользователю заменить существующий текст новым текстом, если исключение текущего выбора не приведет к тому, что текст не будет ниже предела текста.

Эта функция заменяет [LimitText](#limittext) в Win32.

Для получения дополнительной информации см. [EM_SETLIMITTEXT](/windows/win32/Controls/em-setlimittext) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

## <a name="ceditsetmargins"></a><a name="setmargins"></a>CEdit::SetMargins

Вызовите этот метод, чтобы установить левую и правую поля этого элемента управления правки.

```cpp
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>Параметры

*nСлева*<br/>
Ширина нового левого края, в пикселях.

*nПраво*<br/>
Ширина нового правого края, в пикселях.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Эта функция-член доступна начиная с Windows 95 и Windows NT 4.0.

Для получения дополнительной информации смотрите [EM_SETMARGINS](/windows/win32/Controls/em-setmargins) в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

## <a name="ceditsetmodify"></a><a name="setmodify"></a>CEdit::SetModify

Вызовите эту функцию, чтобы установить или очистить измененный флаг для управления редактировкой.

```cpp
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*bИзменено*<br/>
Значение TRUE указывает на то, что текст был изменен, а значение FALSE указывает на то, что он не изменяется. По умолчанию модифицированный флаг устанавливается.

### <a name="remarks"></a>Remarks

Измененный флаг указывает, был ли изменен текст в элементе управления редактирования. Он автоматически устанавливается всякий раз, когда пользователь изменяет текст. Его значение может быть получено с помощью функции участника [GetModify.](#getmodify)

Для получения дополнительной информации смотрите [EM_SETMODIFY](/windows/win32/Controls/em-setmodify) в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::GetModify](#getmodify).

## <a name="ceditsetpasswordchar"></a><a name="setpasswordchar"></a>CEdit::SetPasswordChar

Вызов эту функцию для установки или удаления символа пароля отображается в элемент управления редактированием, когда пользователь вводит текст.

```cpp
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>Параметры

*Ch*<br/>
Определяет символ, который будет отображаться вместо символа, набранного пользователем. Если *ch* раподрается 0, отображаются фактические символы, набранные пользователем.

### <a name="remarks"></a>Remarks

При наборе символа пароля этот символ отображается для каждого символа, который вводит пользователь.

Эта функция члена не влияет на многолиневой элемент управления дейтом.

Когда `SetPasswordChar` функция участника вызывается, `CEdit` перерисовывайте все видимые символы с помощью символа, указанного *ch.*

Если элемент управления редактированием создается со [стилем ES_PASSWORD,](styles-used-by-mfc.md#edit-styles) символ пароля <strong>\*</strong>по умолчанию устанавливается на звездочку (). Этот стиль удаляется, если `SetPasswordChar` называется с *ch* установлен на 0.

Для получения дополнительной информации см. [EM_SETPASSWORDCHAR](/windows/win32/Controls/em-setpasswordchar) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

## <a name="ceditsetreadonly"></a><a name="setreadonly"></a>CEdit::SetReadOnly

Вызывает эту функцию, чтобы установить только для чтения состояние элемента управления редактировать.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*bReadOnly*<br/>
Определяет, следует ли установить или удалить только для чтения состояние элемента управления редитом. Значение TRUE устанавливает состояние для чтения только; значение FALSE устанавливает состояние для чтения/записи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция выполняется успешно, или 0, если происходит ошибка.

### <a name="remarks"></a>Remarks

Текущую настройку можно найти, проверив [ES_READONLY](styles-used-by-mfc.md#edit-styles) флаг в обратном значении [CWnd::GetStyle](cwnd-class.md#getstyle).

Для получения дополнительной информации см. [EM_SETREADONLY](/windows/win32/Controls/em-setreadonly) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

## <a name="ceditsetrect"></a><a name="setrect"></a>CEdit::SetRect

Вызовите эту функцию, чтобы установить размеры прямоугольника с помощью указанных координат.

```cpp
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру или `CRect` объект, который определяет новые размеры прямоугольника форматирования.

### <a name="remarks"></a>Remarks

Этот элемент обрабатывается только несколькими элементами управления элементами действенного элементов.

Используйте `SetRect` для установки прямоугольника форматирования многолинейного элемента управления правкой. Прямоугольник форматирования является ограничивающим прямоугольником текста, который не зависит от размера окна управления редактированием. При первом создании элемента управления правки для отправления является таким же, как и область клиента в окне управления правка. Используя функцию `SetRect` члена, приложение может сделать прямоугольник форматирования больше или меньше, чем окно управления правки.

Если элемент управления редактирования не имеет панели прокрутки, текст будет обрезан, а не завернут, если прямоугольник форматирования больше окна. Если элементаруемый контроль содержит границу, прямоугольник форматирования уменьшается на размер границы. При настройке прямоугольника, `GetRect` возвращенного функцией члена, необходимо удалить размер границы перед `SetRect`прохождением прямоугольника.

При `SetRect` вызове текст элемента управления редактирования также переформатируется и перенаотображается.

Для получения дополнительной информации смотрите [EM_SETRECT](/windows/win32/Controls/em-setrect) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

## <a name="ceditsetrectnp"></a><a name="setrectnp"></a>CEdit::SetRectNP

Вызовите эту функцию, чтобы установить прямоугольник форматирования многолиневого элемента управления правкой.

```cpp
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру или `CRect` объект, который определяет новые размеры прямоугольника.

### <a name="remarks"></a>Remarks

Прямоугольник форматирования является ограничивающим прямоугольником текста, который не зависит от размера окна управления редактированием.

`SetRectNP`идентичен `SetRect` функции элемента, за исключением того, что окно управления отсеиваю не перерисовано.

При первом создании элемента управления правки для отправления является таким же, как и область клиента в окне управления правка. Вызывая `SetRectNP` функцию участника, приложение может сделать прямоугольник форматирования больше или меньше, чем окно управления правки.

Если элемент управления редактирования не имеет панели прокрутки, текст будет обрезан, а не завернут, если прямоугольник форматирования больше окна.

Этот элемент обрабатывается только несколькими элементами управления элементами действенного элементов.

Для получения дополнительной информации смотрите [EM_SETRECTNP](/windows/win32/Controls/em-setrectnp) в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::SetRect](#setrect).

## <a name="ceditsetsel"></a><a name="setsel"></a>CEdit::SetSel

Вызов исчерпнивайте эту функцию, чтобы выбрать диапазон символов в элементауправления редактирования.

```cpp
void SetSel(
    DWORD dwSelection,
    BOOL bNoScroll = FALSE);

void SetSel(
    int nStartChar,
    int nEndChar,
    BOOL bNoScroll = FALSE);
```

### <a name="parameters"></a>Параметры

*dwВыбор*<br/>
Укажите исходное положение в слове низкого порядка и исходное положение в слове высокого порядка. Если слово с низким порядком равен 0, а слово высокого порядка -1, выбирается весь текст в элементе управления редактирования. Если слово с низким заказом -1 удаляется, любой текущий выбор удаляется.

*bNoScroll*<br/>
Указывает, следует ли прокручивать карету в поле зрения. Если FALSE, карета прокручивается в поле зрения. Если правда, карета не прокручивается в поле зрения.

*nStartChar*<br/>
Определяет исходную позицию. Если *nStartChar* равен 0, а *nEndChar* - -1, выбирается весь текст в элементе управления редактированием. Если *nStartChar* -1, любой текущий выбор удаляется.

*nEndChar*<br/>
Определяет конечную позицию.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации смотрите [EM_SETSEL](/windows/win32/Controls/em-setsel) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CEdit::GetSel](#getsel).

## <a name="ceditsettabstops"></a><a name="settabstops"></a>CEdit::SetTabStops

Вызов ими функции для установки остановок вкладок в многолинейном элементе управления действенной работой.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Параметры

*cxEachStop*<br/>
Указывает, что остановки вкладок должны быть установлены на каждом *cxEachStop* диалогединиц.

*nTabStops*<br/>
Упоняет количество остановок вкладок, содержащихся в *rgTabStops*. Это число должно быть больше, чем 1.

*rgTabStops*<br/>
Указывает на массив неподписанных целых рядов с указанием остановки вкладки в единицах диалогов. Единица диалога представляет собой горизонтальное или вертикальное расстояние. Один горизонтальный блок диалога равен одной четверти текущего блока ширины базы диалога, а 1 вертикальный блок диалога равен одной восьмой текущей единицы базовой высоты диалога. Базовые единицы диалогов вычисляются на основе высоты и ширины шрифта текущей системы. Функция `GetDialogBaseUnits` Windows возвращает текущие базовые единицы диалогов в пиксели.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вкладки были установлены; в противном случае 0.

### <a name="remarks"></a>Remarks

Когда текст скопирован на элемент управления редактирования с несколькими строками, любой символ вкладок в тексте приведет к тому, что пространство будет сгенерировано до следующей остановки вкладки.

Чтобы установить стопы вкладок до размера по умолчанию 32 единиц диалогов, вызовите безпаралистную версию этой функции участника. Чтобы установить вкладку останавливается до размера, кроме 32, позвоните в версию с параметром *cxEachStop.* Чтобы установить стопы вкладок на массив размеров, используйте версию с двумя параметрами.

Эта функция члена обрабатывается только несколькими элементами управления элементами действенности.

`SetTabStops`не перерисовывает автоматически окно отсваки. Если вы измените остановки вкладки для текста, уже наемного элемента, позвоните [CWnd::InvalidateRect,](cwnd-class.md#invalidaterect) чтобы перерисовать окно редактирования.

Для получения дополнительной информации смотрите [EM_SETTABSTOPS](/windows/win32/Controls/em-settabstops) и [GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) в Windows SDK.

### <a name="example"></a>Пример

  Смотрите пример [CEditView::SetTabStops](ceditview-class.md#settabstops).

## <a name="ceditshowballoontip"></a><a name="showballoontip"></a>CEdit::ShowBalloonTip

Отображает наконечник шара, связанный с текущим управлением отсеивателя.

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
|*pEditBalloonTip*|(в) Указатель на структуру [EDITBALLOONTIP,](/windows/win32/api/commctrl/ns-commctrl-editballoontip) описывающий наконечник шара.|
|*lpszНазвание*|(в) Указатель на строку Unicode, которая содержит название наконечника шара.|
|*lpszText*|(в) Указатель на строку Unicode, содержащую текст наконечника шара.|
|*ttiIcon*|(в) **INT,** который определяет тип значка, чтобы связать с кончиком шара. Значение по умолчанию TTI_NONE. Для получения дополнительной `ttiIcon` информации [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) см.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Эта функция отправляет [EM_SHOWBALLOONTIP](/windows/win32/Controls/em-showballoontip) сообщение, которое описано в SDK Windows. Для получения дополнительной информации см [Edit_ShowBalloonTip.](/windows/win32/api/commctrl/nf-commctrl-edit_showballoontip)

### <a name="example"></a>Пример

Следующий пример кода определяет `m_cedit`переменную, которая используется для доступа к текущему элементу управления отсеиваниями. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>Пример

Следующий пример кода отображает наконечник шара для управления отсеивателями. [Метод CEdit::ShowBalloonTip](#showballoontip) определяет текст наконечника заголовка и шара.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

## <a name="ceditundo"></a><a name="undo"></a>CEdit::Undo

Вызовите эту функцию, чтобы отменить последнюю операцию управления отсеивание.

```
BOOL Undo();
```

### <a name="return-value"></a>Возвращаемое значение

Для управления элементами реады одной строки значение возврата всегда ненулевое. Для управления элемента реады с несколькими строками значение возврата неявляется, если операция отстойна, или 0, если операция отстойна.

### <a name="remarks"></a>Remarks

Операция отступоровая также может быть отменена. Например, можно восстановить удаленный текст с `Undo`первым вызовом. До тех пор, пока не будет операции редактирования, вы можете удалить `Undo`текст снова со вторым вызовом.

Для получения дополнительной информации [EM_UNDO](/windows/win32/Controls/em-undo) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Пример CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](cwnd-class.md)<br/>
[Класс CButton](cbutton-class.md)<br/>
[Класс CComboBox](ccombobox-class.md)<br/>
[Класс CListBox](clistbox-class.md)<br/>
[Класс CScrollBar](cscrollbar-class.md)<br/>
[Класс CStatic](cstatic-class.md)<br/>
[Класс CDialog](cdialog-class.md)
