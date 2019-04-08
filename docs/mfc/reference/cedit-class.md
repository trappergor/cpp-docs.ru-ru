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
ms.openlocfilehash: 45c03d142c34186660aa2715081ffb0f45e85ccc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773753"
---
# <a name="cedit-class"></a>CEdit Class

Предоставляет функции элемента управления редактированием Windows.

## <a name="syntax"></a>Синтаксис

```
class CEdit : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CEdit::CEdit](#cedit)|Создает `CEdit` объект элемента управления.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CEdit::CanUndo](#canundo)|Определяет, можно ли отменить операцию управления ввода.|
|[CEdit::CharFromPos](#charfrompos)|Возвращает индексы строки и символ для символа, ближайшего к заданной позиции.|
|[CEdit::Clear](#clear)|Операции удаления (очищает) текущее выделение (если таковые имеются) в политике изменения в элемент управления.|
|[CEdit::Copy](#copy)|Копирует текущее выделение (если таковые имеются) в элементе управления в буфер обмена в формате CF_TEXT.|
|[CEdit::Create](#create)|Создает элемент управления Windows и присоединяет его к `CEdit` объекта.|
|[CEdit::Cut](#cut)|Управлять текущее выделение (если таковые имеются) в политике изменения в операции удаления (порезов) и копирует удаленный текст в буфер обмена в CF_TEXT формат.|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Сбрасывает элемент управления (очищает) флаг отмены изменения.|
|[CEdit::FmtLines](#fmtlines)|Задает включение обратимого разрыв строки символов или отключить в элементе управления редактирования несколько строк.|
|[CEdit::GetCueBanner](#getcuebanner)|Извлекает текст, который отображается как текст подсказки, то есть совет, в элемент управления редактированием, когда элемент управления является пустым и не имеет фокуса.|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Определяет верхний видимой строки в элемент управления редактированием.|
|[CEdit::GetHandle](#gethandle)|Извлекает дескриптор памяти, в данный момент для редактирования многострочного элемента управления.|
|[CEdit::GetHighlight](#gethighlight)|Возвращает индексы начальный и конечный символы в диапазоне текста, который будет выделен в текущем элементе управления.|
|[CEdit::GetLimitText](#getlimittext)|Получает максимальный объем текста, это `CEdit` может содержать.|
|[CEdit::GetLine](#getline)|Получает строку текста из элемента управления.|
|[CEdit::GetLineCount](#getlinecount)|Возвращает число строк в элементе управления edit несколько строк.|
|[CEdit::GetMargins](#getmargins)|Возвращает левое и правое поля для этого `CEdit`.|
|[CEdit::GetModify](#getmodify)|Определяет, были ли изменены содержимое элемента управления edit.|
|[CEdit::GetPasswordChar](#getpasswordchar)|Возвращает знак пароля, отображается в элементе управления редактирования, когда пользователь вводит текст.|
|[CEdit::GetRect](#getrect)|Получает прямоугольника форматирования элемента управления edit.|
|[CEdit::GetSel](#getsel)|Возвращает позиции первого и последнего символов текущего выделения в элементе управления редактирования.|
|[CEdit::HideBalloonTip](#hideballoontip)|Скрывает все всплывающей подсказке, связанной с текущего элемента управления edit.|
|[CEdit::LimitText](#limittext)|Ограничивает длину текста, который пользователь может ввести в элемент управления.|
|[CEdit::LineFromChar](#linefromchar)|Получает номер строки, содержащей символ с указанным индексом.|
|[CEdit::LineIndex](#lineindex)|Получает индекс строки в элементе управления редактирования несколько строк.|
|[CEdit::LineLength](#linelength)|Получает длину строки в элемент управления редактированием.|
|[CEdit::LineScroll](#linescroll)|Прокрутка текста элемента управления edit несколько строк.|
|[CEdit::Paste](#paste)|Вставляет данные из буфера обмена в элемент управления в текущей позиции курсора. Данные вставляются только в том случае, если буфер обмена содержит данные в формате CF_TEXT.|
|[CEdit::PosFromChar](#posfromchar)|Извлекает координаты верхнего левого угла символ с указанным индексом.|
|[CEdit::ReplaceSel](#replacesel)|Заменяет текущее выделение в элемент управления редактированием с указанным текстом.|
|[CEdit::SetCueBanner](#setcuebanner)|Задает текст, который отображается как текст подсказки, то есть совет, в элемент управления редактированием, когда элемент управления является пустым и не имеет фокуса.|
|[CEdit::SetHandle](#sethandle)|Задает дескриптор для локальной памяти, который будет использоваться элементом управления редактирования несколько строк.|
|[CEdit::SetHighlight](#sethighlight)|Основные особенности текст, отображаемый в текущий диапазон элемента управления edit.|
|[CEdit::SetLimitText](#setlimittext)|Задает максимальный объем текста, это `CEdit` может содержать.|
|[CEdit::SetMargins](#setmargins)|Задает левое и правое поля для данного `CEdit`.|
|[CEdit::SetModify](#setmodify)|Устанавливает или снимает флаг изменения элемента управления редактирования.|
|[CEdit::SetPasswordChar](#setpasswordchar)|Задает или удаляет знак пароля, отображается в элементе управления редактирования, когда пользователь вводит текст.|
|[CEdit::SetReadOnly](#setreadonly)|Задает состояние только для чтения элемент управления редактированием.|
|[CEdit::SetRect](#setrect)|Задает прямоугольника форматирования элемента управления edit несколько строк и обновляет элемент управления.|
|[CEdit::SetRectNP](#setrectnp)|Задает прямоугольника форматирования элемента управления редактирования многострочного без перерисовка окна элемента управления.|
|[CEdit::SetSel](#setsel)|Выбирает диапазон символов в элемент управления редактированием.|
|[CEdit::SetTabStops](#settabstops)|Наборы табуляции в многострочного поля ввода.|
|[CEdit::ShowBalloonTip](#showballoontip)|Отображает всплывающую подсказку, которая связана с текущего элемента управления edit.|
|[CEdit::Undo](#undo)|Отменяет последнюю операцию управления ввода.|

## <a name="remarks"></a>Примечания

Элемент управления редактированием — прямоугольной дочернее окно, в котором пользователь может ввести текст.

Элемент управления редактированием можно создать из шаблона диалогового окна или непосредственно в коде. В обоих случаях сначала вызовите конструктор `CEdit` для создания `CEdit` объекта, а затем вызовите [создать](#create) функция-член для создания Windows редактирование элемента управления и присоединить его к `CEdit` объекта.

Построение может быть задачей в класс, производный от `CEdit`. Создание конструктора для производного класса, а также вызова `Create` из в конструкторе.

`CEdit` наследует важные функциональные возможности из `CWnd`. Задание и получение текста из `CEdit` , используйте `CWnd` функции-члены [SetWindowText](cwnd-class.md#setwindowtext) и [GetWindowText](cwnd-class.md#getwindowtext), какие set или get все содержимое изменения управления, даже если он Представляет многострочный элемент управления. Строки текста в многострочном элементе управления разделяются последовательности символов «\r\n». Кроме того, если многострочный элемент управления редактированием, получение и задание часть текста элемента управления путем вызова `CEdit` функции-члены [GetLine](#getline), [SetSel](#setsel), [GetSel](#getsel)и [ ReplaceSel](#replacesel).

Если вы хотите обрабатывать сообщения Windows уведомления, отправленные элемент управления редактированием с родительским (обычно класс, производный от `CDialog`), добавить схему сообщений входа и обработчик сообщений функцию-член в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

  **ON_**_уведомления_**(** _идентификатор_**,** _memberFxn_ **)**

где `id` указывает идентификатор дочернего окна элемента управления, отправляющего уведомление, и `memberFxn` имя функции-члена родительской вы написали для обработки уведомления.

Родительский прототип функции выглядит следующим образом:

**afx_msg** void memberFxn **();**

Ниже приведен список потенциальных записей карты и описание вариантов, в которых они бы отправлены родительским.

- ON_EN_CHANGE пользователя были предприняты никакие действие, которое может изменен текст в элемент управления редактированием. В отличие от EN_UPDATE сообщение уведомления это сообщение уведомления отправляется после Windows обновляет соответствующие элементы.

- ON_EN_ERRSPACE поле ввода не удается выделить достаточно памяти для выполнения конкретного запроса.

- ON_EN_HSCROLL пользователь щелкает элемент управления редактирования горизонтальную полосу прокрутки. Родительское окно получает уведомление до обновления экрана.

- ON_EN_KILLFOCUS поле ввода теряет фокус ввода.

- ON_EN_MAXTEXT текущего вставки превысило указанное число символов для элемента управления редактирования и был усечен. Также отправляется, когда элемент управления редактированием не имеет стиль ES_AUTOHSCROLL и количество символов вставляемого превышает ширину элемента управления редактирования. Также отправляется, когда элемент управления редактированием не имеет стиль ES_AUTOVSCROLL и общее число строк, полученный в результате вставки текста приведет к превышению высота элемента управления.

- ON_EN_SETFOCUS отправляется, когда элемент управления редактированием получает фокус ввода.

- ON_EN_UPDATE поле ввода — об изменении отображаемого текста. Отправлено после форматирования текста элемента управления, но до его экраны текст таким образом, может быть изменен размер окна, при необходимости.

- ON_EN_VSCROLL пользователь щелкает элемент управления редактированием вертикальной полосы прокрутки. Родительское окно получает уведомление до обновления экрана.

Если вы создаете `CEdit` объекта в диалоговом окне `CEdit` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

Если вы создаете `CEdit` объект из ресурса с помощью редактора диалоговых окон, диалоговых окон `CEdit` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

Если вы создаете `CEdit` объекта в окне, также может потребоваться уничтожить его. Если вы создаете `CEdit` объект в стеке, он будет удален автоматически. При создании `CEdit` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его, когда пользователь закроет Windows элемента управления edit. Если выделять память в `CEdit` объекта, переопределить `CEdit` деструктор для удаления из выделений.

Чтобы изменить стили, определенные в элемент управления редактирования (например, ES_READONLY) необходимо отправить определенных сообщений на элемент управления, вместо использования [ModifyStyle](cwnd-class.md#modifystyle). См. в разделе [изменение стилей элемента управления](/windows/desktop/Controls/edit-control-styles) в Windows SDK.

Дополнительные сведения о `CEdit`, см. в разделе [элементов управления](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="canundo"></a>  CEdit::CanUndo

Вызывайте эту функцию, чтобы определить, может ли отменить последнюю операцию редактирования.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если последнюю операцию редактирования могут быть отменены путем вызова `Undo` функция-член; 0, если он не может быть отменена.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_CANUNDO](/windows/desktop/Controls/em-canundo) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::Undo](#undo).

##  <a name="cedit"></a>  CEdit::CEdit

Создает объект `CEdit`.

```
CEdit();
```

### <a name="remarks"></a>Примечания

Используйте [создать](#create) для создания элемента управления edit Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

##  <a name="charfrompos"></a>  CEdit::CharFromPos

Вызывайте эту функцию для получения отсчитываемый от нуля и индексы символов символа, ближайшее к указанной точке в это `CEdit` элемента управления

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Координаты точки в клиентской области объекта `CEdit` объекта.

### <a name="return-value"></a>Возвращаемое значение

Индекс символа в СЛОВЕ низкого порядка и индекс строки в старшее слово.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Эта функция-член — доступны начиная с Windows 95 и Windows NT 4.0.

Дополнительные сведения см. в разделе [EM_CHARFROMPOS](/windows/desktop/Controls/em-charfrompos) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

##  <a name="clear"></a>  CEdit::Clear

Вызывайте эту функцию, чтобы удалить (clear) текущее выделение (если таковые имеются) в элементе управления.

```
void Clear();
```

### <a name="remarks"></a>Примечания

Удаления, выполненных `Clear` можно отменить, вызвав [отменить](#undo) функция-член.

Чтобы удалить текущее выделение и помещает удаленные содержимое в буфер обмена, вызовите [Вырезать](#cut) функция-член.

Дополнительные сведения см. в разделе [WM_CLEAR](/windows/desktop/dataxchg/wm-clear) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

##  <a name="copy"></a>  CEdit::Copy

Вызывайте эту функцию для копирование текущего выделения (если таковые имеются) в элементе управления в буфер обмена в формате CF_TEXT.

```
void Copy();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [WM_COPY](/windows/desktop/dataxchg/wm-copy) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

##  <a name="create"></a>  CEdit::Create

Создает элемент управления Windows и присоединяет его к `CEdit` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль элемента управления поля ввода. Применить любое сочетание [изменение стилей](styles-used-by-mfc.md#edit-styles) к элементу управления.

*rect*<br/>
Задает размер и положение элемента управления поля ввода. Может быть `CRect` объекта или `RECT` структуры.

*pParentWnd*<br/>
Указывает родительскому окну элемента редактирования (обычно `CDialog`). Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления поля ввода.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

При создании `CEdit` объекта в два этапа. Во-первых, вызовите `CEdit` конструктора, а затем вызовите метод `Create`, который создает элемент управления Windows и присоединяет его к `CEdit` объекта.

Когда `Create` выполняет, Windows отправляет [WM_NCCREATE](/windows/desktop/winmsg/wm-nccreate), [WM_NCCALCSIZE](/windows/desktop/winmsg/wm-nccalcsize), [WM_CREATE](/windows/desktop/winmsg/wm-create), и [WM_GETMINMAXINFO](/windows/desktop/winmsg/wm-getminmaxinfo) сообщения в элемент управления редактирования.

Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), и [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить обработку сообщения по умолчанию, являются производными от класса `CEdit`, добавить схему сообщений к новому классу и переопределить выше функции-члены обработчика сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.

Примените следующий [стили окна](styles-used-by-mfc.md#window-styles) для элемента управления.

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_GROUP для группировки элементов управления

- WS_TABSTOP включать управления редактированием в порядок следования

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

##  <a name="cut"></a>  CEdit::Cut

Вызывайте эту функцию для удаления (Вырезать) текущего выделения (если таковые имеются) в элементе управления и скопируйте в буфер обмена в формате CF_TEXT удаленного текста.

```
void Cut();
```

### <a name="remarks"></a>Примечания

Удаления, выполненных `Cut` можно отменить, вызвав [отменить](#undo) функция-член.

Чтобы удалить текущее выделение, не помещая удаляемый текст в буфер обмена, вызовите [Очистить](#clear) функция-член.

Дополнительные сведения см. в разделе [WM_CUT](/windows/desktop/dataxchg/wm-cut) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer

Вызывайте эту функцию, чтобы сбросить (Очистить) флаг отмены элемента управления edit.

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Примечания

Поле ввода, теперь смогут отменяет последнюю операцию. Этот флаг отмены имеет значение каждый раз, когда операции в элементе управления редактирования могут быть отменены.

Флаг отмены будет автоматически очищен каждый раз, когда [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) или [метод](#sethandle) `CWnd` функции-члены вызываются.

Дополнительные сведения см. в разделе [EM_EMPTYUNDOBUFFER](/windows/desktop/Controls/em-emptyundobuffer) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

##  <a name="fmtlines"></a>  CEdit::FmtLines

Вызовите эту функцию для задания включения обратимого разрыв строки символов или отключить в элементе управления редактирования несколько строк.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>Параметры

*bAddEOL*<br/>
Указывает, должны быть вставлены обратимо разрыв строки символов. Значение TRUE вставляет символы; значение FALSE удаляет их.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если все форматирование происходит; в противном случае 0.

### <a name="remarks"></a>Примечания

Мягкий перенос состоит из двух символы возврата каретки и перевода строки, вставленной в конце строки, разорвано из-за перенос слов. Разрыв строки жесткого состоит из одного символ возврата каретки и перевода строки. Строки, которые заканчиваются разрыв строки жесткого не затрагивает `FmtLines`.

Windows будет отвечать только в том случае, если `CEdit` объект является элементом управления редактирования несколько строк.

`FmtLines` влияет только на буфер, возвращенный [GetHandle](#gethandle) и текст, возвращенный [WM_GETTEXT](/windows/desktop/winmsg/wm-gettext). Он не оказывает влияния на отображение текста в элементе управления редактирования.

Дополнительные сведения см. в разделе [EM_FMTLINES](/windows/desktop/Controls/em-fmtlines) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

##  <a name="getcuebanner"></a>  CEdit::GetCueBanner

Извлекает текст, который отображается как текст подсказки, то есть совет, в элемент управления редактированием, когда элемент управления является пустым.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
[out] Указатель на строку, содержащую текст подсказки.

*cchText*<br/>
[in] Число символов, которые могут быть получены. Это число включает завершающий нуль-символ.

### <a name="return-value"></a>Возвращаемое значение

Для первой перегрузке значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

Для второй перегрузке [CString](../../atl-mfc-shared/using-cstring.md) , содержащее текст подсказки, если метод выполнен успешно; в противном случае — пустая строка (»»).

### <a name="remarks"></a>Примечания

Этот метод отправляет [EM_GETCUEBANNER](/windows/desktop/Controls/em-getcuebanner) сообщения, который описан в пакете Windows SDK. Дополнительные сведения см. в разделе [Edit_GetCueBannerText](/windows/desktop/api/commctrl/nf-commctrl-edit_getcuebannertext) макрос.

##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine

Вызывайте эту функцию, чтобы определить верхний видимой строки в элемент управления редактированием.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс верхней видимой строкой. Для элементов управления одной строкой возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_GETFIRSTVISIBLELINE](/windows/desktop/Controls/em-getfirstvisibleline) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

##  <a name="gethandle"></a>  CEdit::GetHandle

Вызывайте эту функцию, чтобы получить дескриптор памяти, выделенных в данный момент для редактирования многострочного элемента управления.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор локальной памяти, который идентифицирует буфер, содержащий содержимое элемента управления. Если возникает ошибка, например, отправку сообщения к элементу управления одной строкой, возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

Дескриптор является дескриптором локальной памяти, может использоваться любым из **локального** функции памяти Windows, которые принимают локальной памяти обрабатывать как параметр.

`GetHandle` обрабатывается только редактирование многострочных элементов управления.

Вызовите `GetHandle` для редактирования многострочного элемента управления в диалоговом окне только в том случае, если диалоговое окно был создан с установленным флагом стиля DS_LOCALEDIT. Если стиль DS_LOCALEDIT не указан, вы будете получать ненулевое возвращаемое значение, но вы не сможете использовать возвращаемое значение.

> [!NOTE]
> `GetHandle` не будет работать с Windows 95/98. При вызове метода `GetHandle` в Windows 95/98, возвращается значение NULL. `GetHandle` будет работать, как описано в Windows NT 3.51 и более поздних версиях.

Дополнительные сведения см. в разделе [EM_GETHANDLE](/windows/desktop/Controls/em-gethandle) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

##  <a name="gethighlight"></a>  CEdit::GetHighlight

Возвращает индексы первый и последний символы в диапазоне текста, который будет выделен в текущем элементе управления.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*pichStart*|[out] Отсчитываемый от нуля индекс первого символа в диапазоне текста, который будет выделен.|
|*pichEnd*|[out] Отсчитываемый от нуля индекс последнего символа в диапазоне текста, который будет выделен.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [EM_GETHILITE](/windows/desktop/Controls/em-gethilite) сообщения, который описан в пакете Windows SDK. Оба `SetHighlight` и `GetHighlight` включены только сборках ЮНИКОДА.

##  <a name="getlimittext"></a>  CEdit::GetLimitText

Эта функция-член для получения текста предел для данного вызова `CEdit` объекта.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий текст ограничение в TCHARs, для этого `CEdit` объекта.

### <a name="remarks"></a>Примечания

Текст ограничено максимальное текста в TCHARs, принимают поле ввода.

> [!NOTE]
>  Эта функция-член — доступны начиная с Windows 95 и Windows NT 4.0.

Дополнительные сведения см. в разделе [EM_GETLIMITTEXT](/windows/desktop/Controls/em-getlimittext) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

##  <a name="getline"></a>  CEdit::GetLine

Вызывайте эту функцию для получения строки текста из элемента управления и помещает его в *lpszBuffer*.

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

*nIndex*<br/>
Указывает номер строки для извлечения из многострочного поля ввода. Номера строк отсчитываются от нуля; значение 0 задает первую строку. Этот параметр обрабатывается элементом управления одной строкой.

*lpszBuffer*<br/>
Указатель на буфер, который получает копию строки. Первое слово буфера необходимо указать максимальное число TCHARs, которые могут быть скопированы в буфер.

*nMaxLength*<br/>
Указывает максимальное количество символов TCHAR, которые могут быть скопированы в буфер. `GetLine` помещает это значение в первое слово *lpszBuffer* перед вызовом для Windows.

### <a name="return-value"></a>Возвращаемое значение

Число фактически скопированных символов. Возвращаемое значение равно 0, если номер строки, указанный параметром *nIndex* больше, чем число строк в элементе управления.

### <a name="remarks"></a>Примечания

Скопированную строку не содержит знак завершения null.

Дополнительные сведения см. в разделе [EM_GETLINE](/windows/desktop/Controls/em-getline) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::GetLineCount](#getlinecount).

##  <a name="getlinecount"></a>  CEdit::GetLineCount

Вызывайте эту функцию для получения числа строк в элементе управления edit несколько строк.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целое число, содержащее количество строк в несколько строк элемента управления edit. Если текст не введен в поле ввода, возвращаемое значение-1.

### <a name="remarks"></a>Примечания

`GetLineCount` обрабатывается только редактирование многострочных элементов управления.

Дополнительные сведения см. в разделе [EM_GETLINECOUNT](/windows/desktop/Controls/em-getlinecount) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

##  <a name="getmargins"></a>  CEdit::GetMargins

Вызовите эту функцию-член для извлечения левое и правое поля поля ввода.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина левого поля в младшее слово и ширину правого поля в старшее слово.

### <a name="remarks"></a>Примечания

Поля измеряются в пикселях.

> [!NOTE]
>  Эта функция-член — доступны начиная с Windows 95 и Windows NT 4.0.

Дополнительные сведения см. в разделе [EM_GETMARGINS](/windows/desktop/Controls/em-getmargins) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="getmodify"></a>  CEdit::GetModify

Вызывайте эту функцию, чтобы определить, были ли изменены содержимое элемента управления edit.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если содержимое элемента управления редактирования были изменены; 0, если они остаются без изменений.

### <a name="remarks"></a>Примечания

Windows поддерживает внутренний флаг, указывающий, были ли изменены содержимое элемента управления. Данный флаг снят, когда поле ввода сначала создается и может также очистить путем вызова [SetModify](#setmodify) функция-член.

Дополнительные сведения см. в разделе [EM_GETMODIFY](/windows/desktop/Controls/em-getmodify) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar

Вызывайте эту функцию для получения знак пароля, который отображается в элемент управления редактированием, когда пользователь вводит текст.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Задает символ, отображаемый вместо знак, введенный пользователем. Возвращает значение NULL, если существует отсутствует знак пароля.

### <a name="remarks"></a>Примечания

При создании элемента управления редактирования в стиле ES_PASSWORD, библиотеки DLL, которая поддерживает элемент управления определяет знак пароля по умолчанию. Манифест или [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) метод определяет, какие библиотеки DLL поддерживает поле ввода. Если user32.dll поддерживает поле ввода, знак пароля по умолчанию — символ ЗВЕЗДОЧКИ ("*", U + 002A). Если comctl32.dll версии 6 поддерживает поле ввода, символ по умолчанию — ЧЕРНЫЙ КРУГ («●», U + 25CF). Дополнительные сведения о какие библиотеки DLL и версии поддерживает общие элементы управления, см. в разделе [оболочка и версии общих элементов управления](https://msdn.microsoft.com/library/windows/desktop/bb776779).

Этот метод отправляет [EM_GETPASSWORDCHAR](/windows/desktop/Controls/em-getpasswordchar) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

##  <a name="getrect"></a>  CEdit::GetRect

Вызовите эту функцию для получения прямоугольника форматирования элемента управления edit.

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуру, которая получает прямоугольника форматирования.

### <a name="remarks"></a>Примечания

В прямоугольнике форматирования является ограничивающим прямоугольником текста, который не зависит от размера окна элемента управления редактирования.

Могут быть изменены прямоугольника форматирования элемента управления редактирования многострочного [SetRect](#setrect) и [SetRectNP](#setrectnp) функций-членов.

Дополнительные сведения см. в разделе [EM_GETRECT](/windows/desktop/Controls/em-getrect) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::LimitText](#limittext).

##  <a name="getsel"></a>  CEdit::GetSel

Вызывайте эту функцию, чтобы получить начальный и конечный позиций знаков из текущего выделения (если таковые имеются) в элемент управления редактирования, используя параметры или возвращаемое значение.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>Параметры

*nStartChar*<br/>
Ссылка на целое число, получите положение первого символа в текущем выделении.

*nEndChar*<br/>
Ссылка на целое число, получите положение первого символа невыбранные за пределами текущего выделения.

### <a name="return-value"></a>Возвращаемое значение

Версию, которая возвращает значение типа DWORD возвращает значение, содержащее начальную позицию в младшее слово и позицию первого символа невыбранные после окончания выделения в старшее слово.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_GETSEL](/windows/desktop/Controls/em-getsel) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip

Скрывает все всплывающей подсказке, связанной с текущего элемента управления edit.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Эта функция отправляет [EM_HIDEBALLOONTIP](/windows/desktop/Controls/em-hideballoontip) сообщения, который описан в пакете Windows SDK.

##  <a name="limittext"></a>  CEdit::LimitText

Вызывайте эту функцию, чтобы ограничить длину текста, который пользователь может вводить в элемент управления редактированием.

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>Параметры

*nChars*<br/>
Задает длину (в TCHARs) текст, который пользователь может ввести. Если этот параметр равен 0, длина текста присваивается UINT_MAX байт. Это поведение установлено по умолчанию.

### <a name="remarks"></a>Примечания

Изменение текста ограничения ограничивает только текст, который пользователь может ввести. Он не оказывает влияния на любой текст уже в элементе управления, а также влияет на длину текста, копируются в элемент управления редактирования, [SetWindowText](cwnd-class.md#setwindowtext) функции-члена в `CWnd`. Если приложение использует `SetWindowText` функции, чтобы поместить текст в элемент управления редактированием, чем указано в вызове `LimitText`, пользователь может удалять любые текстовые строки в элементе управления редактирования. Тем не менее ограничение текст не позволит пользователю заменять существующий текст новым текстом, если не удалить текущее выделение вызывает текста упадет ниже предела текста.

> [!NOTE]
>  В Win32 (Windows NT и Windows 95/98), [SetLimitText](#setlimittext) заменяет эту функцию.

Дополнительные сведения см. в разделе [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

##  <a name="linefromchar"></a>  CEdit::LineFromChar

Вызывайте эту функцию, чтобы получить номер строки, содержащей символ с указанным индексом.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Содержит отсчитываемый от нуля индекс значение для требуемого знака в тексте элемента управления, или значение -1. Если *nIndex* равно -1, он задает текущую строку, то есть строки, содержащей курсор.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля номер строки, содержащей индекс символа, определяемое *nIndex*. Если *nIndex* равно -1, возвращается номер строки, который содержит первый символ выделения. Если ничего не выбрано, возвращается текущий номер строки.

### <a name="remarks"></a>Примечания

Индекс символа — количество символов с начала элемента управления.

Эта функция-член используется только элементами управления редактирования несколько строк.

Дополнительные сведения см. в разделе [EM_LINEFROMCHAR](/windows/desktop/Controls/em-linefromchar) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

##  <a name="lineindex"></a>  CEdit::LineIndex

Вызывайте эту функцию для извлечения индекса символа строки в элементе управления редактирования несколько строк.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>Параметры

*бота*<br/>
Содержит значение индекса для нужной строке в тексте элемента управления, или значение -1. Если *бота* равно -1, он задает текущую строку, то есть строки, содержащей курсор.

### <a name="return-value"></a>Возвращаемое значение

Индекс строки, указанной в *бота* или -1, если номер строки больше, чем число строк в элементе управления.

### <a name="remarks"></a>Примечания

Индекс символа — количество символов с начала элемента управления редактированием для указанной строки.

Эта функция-член обрабатывается только редактирование многострочных элементов управления.

Дополнительные сведения см. в разделе [EM_LINEINDEX](https://msdn.microsoft.com/library/windows/desktop/bb761611) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

##  <a name="linelength"></a>  CEdit::LineLength

Получает длину строки в элемент управления редактированием.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>Параметры

*бота*<br/>
Отсчитываемый от нуля индекс символа в строке, длина которого требуется получить. Значение по умолчанию — -1.

### <a name="return-value"></a>Возвращаемое значение

Для элементов управления одной строкой возвращаемое значение имеет длину, в TCHARs, текст в элементе управления.

Для элементов управления многострочное поле ввода, возвращается длина строки, номер, в TCHARs, *бота* параметра. Для текста ANSI длина — число байтов в строке; для текста в Юникоде длина — число символов в строке. Длина не включает символ возврата каретки в конце строки.

Если *бота* параметр больше, чем количество символов в элементе управления, возвращаемое значение равно нулю.

Если *бота* параметра равно -1, возвращаемое число невыбранных символов в строки, содержащие выбранные символы. Например если выделение распространяется из одной строки через восьмой символ в конце следующей строке четвертый символ, возвращаемое значение — 10. То есть три символа на первую строку и семь на следующей.

Дополнительные сведения о типе TCHAR см. в строке TCHAR таблицы в [типы данных Windows](/windows/desktop/WinProg/windows-data-types).

### <a name="remarks"></a>Примечания

Этот метод поддерживается [EM_LINELENGTH](/windows/desktop/Controls/em-linelength) сообщения, который описан в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::LineIndex](#lineindex).

##  <a name="linescroll"></a>  CEdit::LineScroll

Вызывайте эту функцию для прокрутки текст элемента управления edit несколько строк.

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>Параметры

*nLines*<br/>
Указывает количество строк для прокрутки по вертикали.

*nChars*<br/>
Указывает количество позиций знаков для прокрутки по горизонтали. Это значение игнорируется, если для элемента управления редактирования стиля ES_RIGHT или ES_CENTER.

### <a name="remarks"></a>Примечания

Эта функция-член, обрабатывается только редактирование многострочных элементов управления.

Поле ввода не прокручивается по вертикали после последней строки текста в элементе управления. Если текущий строка плюс количество строк, определяемое *nLines* превышает общее число строк в элементе управления, значение корректируются таким образом, чтобы в последней строке элемента управления редактирования прокручиваются к верхней части окна элемента управления edit.

`LineScroll` используется для прокрутки по горизонтали после последнего символа любой строки.

Дополнительные сведения см. в разделе [EM_LINESCROLL](/windows/desktop/Controls/em-linescroll) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::GetFirstVisibleLine](#getfirstvisibleline).

##  <a name="paste"></a>  CEdit::Paste

Вызывайте эту функцию для вставки данных из буфера обмена в `CEdit` в позиции курсора.

```
void Paste();
```

### <a name="remarks"></a>Примечания

Данные вставляются только в том случае, если буфер обмена содержит данные в формате CF_TEXT.

Дополнительные сведения см. в разделе [WM_PASTE](/windows/desktop/dataxchg/wm-paste) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

##  <a name="posfromchar"></a>  CEdit::PosFromChar

Вызывайте эту функцию для получения позиции (в левом верхнем углу) определенный символ в рамках этого `CEdit` объекта.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>Параметры

*NChar*<br/>
Отсчитываемый от нуля индекс заданного символа.

### <a name="return-value"></a>Возвращаемое значение

Координаты верхнего левого угла символ, заданный параметром *nChar*.

### <a name="remarks"></a>Примечания

Символ, заданный, задав значение его отсчитываемый от нуля индекс. Если *nChar* больше индекса последнего символа в этом `CEdit` объекта, возвращаемое значение, указывающее координаты позиции позицию сразу после последнего символа в этом `CEdit` объекта.

> [!NOTE]
>  Эта функция-член — доступны начиная с Windows 95 и Windows NT 4.0.

Дополнительные сведения см. в разделе [EM_POSFROMCHAR](/windows/desktop/Controls/em-posfromchar) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::LineFromChar](#linefromchar).

##  <a name="replacesel"></a>  CEdit::ReplaceSel

Вызывайте эту функцию для замены текущего выделения в элементе управления редактирования с текстом, указанным по *lpszNewText*.

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>Параметры

*lpszNewText*<br/>
Указатель на заканчивающуюся нулем строку, содержащую текст замены.

*bCanUndo*<br/>
Чтобы указать, что эту функцию можно отменить, значение этого параметра равно TRUE. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

Заменяет только часть текста в элемент управления редактированием. Если вы хотите заменить весь текст, используйте [CWnd::SetWindowText](cwnd-class.md#setwindowtext) функция-член.

Если текущее выделение отсутствует, замещающий текст вставляется в текущем положении курсора.

Дополнительные сведения см. в разделе [EM_REPLACESEL](/windows/desktop/Controls/em-replacesel) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::LineIndex](#lineindex).

##  <a name="setcuebanner"></a>  CEdit::SetCueBanner

Задает текст, который отображается как текст подсказки, или совет, изменения управления, когда элемент управления является пустым.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
[in] Указатель на строку, содержащую подсказки для отображения в элементе управления.

*fDrawWhenFocused*<br/>
[in] Если значение равно FALSE, когда пользователь нажимает кнопку в элементе управления и передает элемент управления фокус баннер подсказки не рисуется.

Если значение равно TRUE, баннер подсказки отображается даже в том случае, если элемент управления имеет фокус. Баннер подсказки исчезает, когда пользователь начинает вводить в элемент управления.

Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [EM_SETCUEBANNER](/windows/desktop/Controls/em-setcuebanner) сообщения, который описан в пакете Windows SDK. Дополнительные сведения см. в разделе [Edit_SetCueBannerTextFocused](/windows/desktop/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) макрос.

### <a name="example"></a>Пример

В следующем примере демонстрируется [CEdit::SetCueBanner](#setcuebanner) метод.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

##  <a name="sethandle"></a>  CEdit::SetHandle

Вызывайте эту функцию для задания в локальную память, который будет использоваться элементом управления редактирования несколько строк.

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>Параметры

*hBuffer*<br/>
Содержит дескриптор локальной памяти. Этот дескриптор должна быть создана после предыдущего вызова [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) функции Windows, с помощью флага LMEM_MOVEABLE. Предполагается, что память содержит строку, завершающуюся символом null. Если это не так, первый байт выделенной памяти должно быть равным 0.

### <a name="remarks"></a>Примечания

Поле ввода будет использовать этот буфер для хранения текста, отображаемого вместо выделения собственного буфера.

Эта функция-член, обрабатывается только редактирование многострочных элементов управления.

Прежде чем приложение задает новый дескриптор памяти, следует использовать [GetHandle](#gethandle) получить дескриптор для текущего буфера памяти и освобождения этой памяти с помощью функции-члена `LocalFree` функции Windows.

`SetHandle` Очищает буфер отмены ( [CanUndo](#canundo) функция-член возвращает 0) и флаг внутреннего изменения ( [GetModify](#getmodify) функция-член возвращает 0). Перерисовывается окна элемента управления edit.

Эта функция-член в элементе управления edit несколько строк в диалоговом окне можно использовать только в том случае, если вы создали диалоговое окно с установленным флагом стиля DS_LOCALEDIT.

> [!NOTE]
> `GetHandle` не будет работать с Windows 95/98. При вызове метода `GetHandle` в Windows 95/98, возвращается значение NULL. `GetHandle` будет работать, как описано в Windows NT 3.51 и более поздних версиях.

Дополнительные сведения см. в разделе [EM_SETHANDLE](/windows/desktop/Controls/em-sethandle), [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc), и [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

##  <a name="sethighlight"></a>  CEdit::SetHighlight

Основные особенности текст, отображаемый в текущий диапазон элемента управления edit.

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ichStart*|[in] Отсчитываемый от нуля индекс первого символа в диапазоне текста для выделения.|
|*ichEnd*|[in] Отсчитываемый от нуля индекс последнего символа в диапазоне текста для выделения.|

### <a name="remarks"></a>Примечания

Этот метод отправляет [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) сообщения, который описан в пакете Windows SDK.  Этот метод отправляет [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) сообщения, который описан в пакете Windows SDK. Оба `SetHighlight` и `GetHighlight` включены только сборках ЮНИКОДА.

##  <a name="setlimittext"></a>  CEdit::SetLimitText

Эта функция-член ограничение текста для этого вызовите `CEdit` объекта.

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>Параметры

*Nмакс.*<br/>
Новое ограничение текста в символах.

### <a name="remarks"></a>Примечания

Текст ограничено максимальное значение в символах, которые могут принимать в элемент управления редактирования текста.

Изменение текста ограничения ограничивает только текст, который пользователь может ввести. Он не оказывает влияния на любой текст уже в элементе управления, а также влияет на длину текста, копируются в элемент управления редактирования, [SetWindowText](cwnd-class.md#setwindowtext) функции-члена в `CWnd`. Если приложение использует `SetWindowText` функции, чтобы поместить текст в элемент управления редактированием, чем указано в вызове `LimitText`, пользователь может удалять любые текстовые строки в элементе управления редактирования. Тем не менее ограничение текст не позволит пользователю заменять существующий текст новым текстом, если не удалить текущее выделение вызывает текста упадет ниже предела текста.

Эта функция заменяет [LimitText](#limittext) в Win32.

Дополнительные сведения см. в разделе [EM_SETLIMITTEXT](/windows/desktop/Controls/em-setlimittext) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="setmargins"></a>  CEdit::SetMargins

Вызовите этот метод, чтобы задать поля левого и правого поля ввода.

```
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>Параметры

*nLeft*<br/>
Ширина нового левое поле в пикселях.

*nRight*<br/>
Ширина нового правое поле в пикселях.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Эта функция-член — доступны начиная с Windows 95 и Windows NT 4.0.

Дополнительные сведения см. в разделе [EM_SETMARGINS](/windows/desktop/Controls/em-setmargins) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="setmodify"></a>  CEdit::SetModify

Вызывайте эту функцию, чтобы задать или очистить измененного флага для элемента управления.

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*bModified*<br/>
Значение TRUE указывает, что текст был изменен, и значение FALSE указывает, что он не меняется. По умолчанию имеет значение измененного флага.

### <a name="remarks"></a>Примечания

Измененного флага указывает, был ли изменен текст внутри элемента управления редактирования. Автоматически устанавливается каждый раз, когда пользователь изменяет текст. Ее значение может быть получено с [GetModify](#getmodify) функция-член.

Дополнительные сведения см. в разделе [EM_SETMODIFY](/windows/desktop/Controls/em-setmodify) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::GetModify](#getmodify).

##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar

Вызывайте эту функцию, чтобы установить или удалить знак пароля, отображаемый в элемент управления редактированием при вводе пользователем текста.

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>Параметры

*CH*<br/>
Задает символ, которые будут отображаться вместо символа, введенного пользователем. Если *ch* равно 0, отображаются фактические символы, введенные пользователем.

### <a name="remarks"></a>Примечания

При знак пароля имеет значение, она отображается этот символ, для все символы пользователь вводит текст.

Эта функция-член не влияет на несколько строк элемента управления edit.

Когда `SetPasswordChar` вызывается функция-член, `CEdit` обновление всех видимых символы, используя символ, заданный параметром *ch*.

Если элемент управления создается с помощью [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) стиля, знак пароля по умолчанию задано значение звездочку ( <strong>\*</strong>). Этот стиль удаляется, если `SetPasswordChar` вызывается с *ch* присвоено значение 0.

Дополнительные сведения см. в разделе [EM_SETPASSWORDCHAR](/windows/desktop/Controls/em-setpasswordchar) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

##  <a name="setreadonly"></a>  CEdit::SetReadOnly

Вызывает эту функцию для задания состояния только для чтения элемент управления редактированием.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*bReadOnly*<br/>
Указывает, следует ли установить или удалить состояние только для чтения элемента управления. Значение TRUE задает состояние только для чтения; значение FALSE задает состояние для чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно, или 0, если ошибка возникла.

### <a name="remarks"></a>Примечания

Текущее значение параметра можно определить путем тестирования [ES_READONLY](styles-used-by-mfc.md#edit-styles) флаг в значение, возвращаемое [CWnd::GetStyle](cwnd-class.md#getstyle).

Дополнительные сведения см. в разделе [EM_SETREADONLY](/windows/desktop/Controls/em-setreadonly) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

##  <a name="setrect"></a>  CEdit::SetRect

Вызывайте эту функцию, чтобы задать размеры прямоугольника, используя указанные координаты.

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуры или `CRect` , указывающий новые размеры прямоугольника форматирования.

### <a name="remarks"></a>Примечания

Этот элемент обрабатывается только редактирование многострочных элементов управления.

Используйте `SetRect` форматирования прямоугольника многострочного элемента управления edit. В прямоугольнике форматирования является ограничивающим прямоугольником текста, который не зависит от размера окна элемента управления редактирования. При создании элемента управления редактирования, прямоугольника форматирования совпадает со значением клиентской области окна элемента управления edit. С помощью `SetRect` функция-член, приложение может установить прямоугольника форматирования больше или меньше окна элемента управления edit.

Если для редактирования элемента управления полосы прокрутки, текст будет обрезана, не заключаются в оболочку, если прямоугольника форматирования становится больше, чем окна. Если элемент управления редактирования содержит границу, прямоугольника форматирования уменьшается размер границы. Если настроить прямоугольнику, возвращенному `GetRect` функция-член, размер границы необходимо удалить, прежде чем передать прямоугольника для `SetRect`.

При `SetRect` вызывается в элемент управления редактирования текста является также переформатированы и повторно.

Дополнительные сведения см. в разделе [EM_SETRECT](/windows/desktop/Controls/em-setrect) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

##  <a name="setrectnp"></a>  CEdit::SetRectNP

Вызовите эту функцию для задания прямоугольника форматирования элемента управления edit несколько строк.

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на `RECT` структуры или `CRect` , указывающий новые размеры прямоугольника.

### <a name="remarks"></a>Примечания

В прямоугольнике форматирования является ограничивающим прямоугольником текста, который не зависит от размера окна элемента управления редактирования.

`SetRectNP` идентичен `SetRect` функцию-член, за исключением того, что не перерисовке окна элемента управления edit.

При создании элемента управления редактирования, прямоугольника форматирования совпадает со значением клиентской области окна элемента управления edit. Путем вызова `SetRectNP` функция-член, приложение может установить прямоугольника форматирования больше или меньше окна элемента управления edit.

Если для редактирования элемента управления полосы прокрутки, текст будет обрезана, не заключаются в оболочку, если прямоугольника форматирования становится больше, чем окна.

Этот элемент обрабатывается только редактирование многострочных элементов управления.

Дополнительные сведения см. в разделе [EM_SETRECTNP](/windows/desktop/Controls/em-setrectnp) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::SetRect](#setrect).

##  <a name="setsel"></a>  CEdit::SetSel

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

*dwSelection*<br/>
Указывает начальную позицию в младшее слово и конечную позицию в старшее слово. Если младшее слово — 0, а старшее слово равно -1, выбирается весь текст в элементе управления. Если младшее слово равно -1, любое текущее выделение удаляется.

*bNoScroll*<br/>
Указывает, является ли курсор должен быть прокручен в представлении. Если значение равно FALSE, курсор в области просмотра. Значение TRUE, если курсор не в области просмотра.

*nStartChar*<br/>
Определяет начальную позицию. Если *nStartChar* равно 0 и *nEndChar* равно -1, все выбранные текст в элементе управления. Если *nStartChar* равно -1, любое текущее выделение удаляется.

*nEndChar*<br/>
Задает конечное положение.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_SETSEL](/windows/desktop/Controls/em-setsel) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEdit::GetSel](#getsel).

##  <a name="settabstops"></a>  CEdit::SetTabStops

Вызовите эту функцию для задания позиции табуляции в элементе управления edit несколько строк.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Параметры

*cxEachStop*<br/>
Указывает, что табуляции должны быть заданы на каждый *cxEachStop* диалоговых единицах.

*nTabStops*<br/>
Указывает количество позициями табуляции, содержащихся в *rgTabStops*. Это число должно быть больше 1.

*rgTabStops*<br/>
Указывается массив целых чисел без знака, указав на вкладке останавливает в диалоговых единицах. Единица размера диалогового окна является горизонтальное или вертикальное расстояние. Единицы диалогового окна по горизонтали равным одной четвертой текущей единице измерения базового ширины диалогового окна, и 1 единицу вертикальной диалоговое окно эквивалентен одну восьмую единиц базовый высоту текущего диалогового окна. Базовые единицы диалогового окна вычисляются в зависимости от высоты и ширины текущего системного шрифта. `GetDialogBaseUnits` Windows функция возвращает базовых единиц текущего диалогового окна в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если были заданы вкладок; в противном случае 0.

### <a name="remarks"></a>Примечания

При копировании текста в элемент управления редактирования многострочного любой символ табуляции в тексте вызовет пространство для создаваемой до следующей позиции табуляции.

Чтобы установить табуляции по умолчанию размер 32 диалоговых единицах, вызова без параметров версии эта функция-член. Чтобы Установка позиций табуляции до размера, отличного от 32, вызовите версию с *cxEachStop* параметра. Чтобы установить табуляции в массив размеров, используйте версию с двумя параметрами.

Эта функция-член обрабатывается только редактирование многострочных элементов управления.

`SetTabStops` не автоматически перерисовать окно редактирования. При изменении позиции табуляции для текста уже в элементе управления, вызовите [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) перерисовывает окно редактирования.

Дополнительные сведения см. в разделе [EM_SETTABSTOPS](/windows/desktop/Controls/em-settabstops) и [GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CEditView::SetTabStops](ceditview-class.md#settabstops).

##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip

Отображает всплывающую подсказку, которая связана с текущего элемента управления edit.

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
|*pEditBalloonTip*|[in] Указатель на [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) структура, описывающая всплывающей подсказки.|
|*lpszTitle*|[in] Указатель на строку Юникода, которая содержит заголовок всплывающей подсказки.|
|*lpszText*|[in] Указатель на строку Юникода, которая содержит текст подсказки.|
|*ttiIcon*|[in] **INT** , указывающий тип значка, связываемый с всплывающей подсказки. Значение по умолчанию — TTI_NONE. Дополнительные сведения см. в разделе `ttiIcon` членом [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) структуры.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Эта функция отправляет [EM_SHOWBALLOONTIP](/windows/desktop/Controls/em-showballoontip) сообщения, который описан в пакете Windows SDK. Дополнительные сведения см. в разделе [Edit_ShowBalloonTip](/windows/desktop/api/commctrl/nf-commctrl-edit_showballoontip) макрос.

### <a name="example"></a>Пример

В следующем примере кода определяет переменную, `m_cedit`, который используется для доступа к текущего элемента управления edit. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>Пример

В следующем примере кода отображает всплывающую подсказку для элемента управления. [CEdit::ShowBalloonTip](#showballoontip) метод задает текст заголовок и всплывающей подсказки.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

##  <a name="undo"></a>  CEdit::Undo

Вызывайте эту функцию для отмены последней операции управления ввода.

```
BOOL Undo();
```

### <a name="return-value"></a>Возвращаемое значение

Для элемента управления одной строкой возвращаемое значение всегда имеет ненулевое значение. Для редактирования многострочного элемента управления, возвращаемое значение не равно нулю, если операция отмены выполнена успешно, или 0, если происходит сбой операции отмены.

### <a name="remarks"></a>Примечания

Также можно отменить операцию отмены. Например, вы можете восстановить удаленный текст с первого вызова `Undo`. До тех пор, пока нет промежуточные операции редактирования, можно удалить текст с использованием второй вызов `Undo`.

Дополнительные сведения см. в разделе [EM_UNDO](/windows/desktop/Controls/em-undo) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[Образец CMNCTRL2 MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](cwnd-class.md)<br/>
[Класс CButton](cbutton-class.md)<br/>
[CComboBox-класс](ccombobox-class.md)<br/>
[CListBox-класс](clistbox-class.md)<br/>
[Класс CScrollBar](cscrollbar-class.md)<br/>
[Класс CStatic](cstatic-class.md)<br/>
[Класс CDialog](cdialog-class.md)
