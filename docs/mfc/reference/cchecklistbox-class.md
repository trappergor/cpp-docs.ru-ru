---
title: Класс Кчекклистбокс
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: cd50711813a3cfc1305cd5558c95e909ddbfc3f2
ms.sourcegitcommit: ab8d7b47b63b62892a1256a09b1324a9a136eccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "78215528"
---
# <a name="cchecklistbox-class"></a>Класс Кчекклистбокс

Предоставляет функции поля со списком Windows.

## <a name="syntax"></a>Синтаксис

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кчекклистбокс:: Кчекклистбокс](#cchecklistbox)|Формирует объект `CCheckListBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кчекклистбокс:: Create](#create)|Создает окно контрольного списка Windows и прикрепляет его к объекту `CCheckListBox`.|
|[Кчекклистбокс::D Равитем](#drawitem)|Вызывается структурой при изменении визуального аспекта поля списка, рисуемого владельцем.|
|[Кчекклистбокс:: enable](#enable)|Включает или отключает элемент поля контрольного списка.|
|[Кчекклистбокс:: Check](#getcheck)|Возвращает состояние флажка элемента.|
|[Кчекклистбокс:: Жетчеккстиле](#getcheckstyle)|Возвращает стиль флажков элемента управления.|
|[Кчекклистбокс:: enable](#isenabled)|Определяет, включен ли элемент.|
|[Кчекклистбокс:: Меасуреитем](#measureitem)|Вызывается структурой при создании поля списка с стилем рисования-прорисовки.|
|[Кчекклистбокс:: Онжетчеккпоситион](#ongetcheckposition)|Вызывается платформой для получения позиции флажка элемента.|
|[Кчекклистбокс:: Сетчекк](#setcheck)|Задает состояние флажка элемента.|
|[Кчекклистбокс:: Сетчеккстиле](#setcheckstyle)|Задает стиль флажков элемента управления.|

## <a name="remarks"></a>Remarks

В поле контрольного списка отображается список элементов, например имена файлов. Каждый элемент в списке имеет флажок рядом с ним, который пользователь может проверить или очистить.

`CCheckListBox` предназначен только для элементов управления, рисуемых владельцем, так как список содержит более текстовых строк. В самом простом поле контрольного списка содержит текстовые строки и флажки, но текст вообще не нужен. Например, у вас может быть список небольших точечных рисунков с флажком рядом с каждым элементом.

Для создания собственного поля контрольного списка необходимо создать собственный класс от `CCheckListBox`. Чтобы получить собственный класс, напишите конструктор для производного класса, а затем вызовите `Create`.

Если требуется работать с сообщениями уведомлений Windows, отправленными списком, в родительский список (обычно это класс, производный от класса [CDialog](../../mfc/reference/cdialog-class.md)), добавьте запись схемы сообщения и функцию-член обработчика сообщений в родительский класс для каждого сообщения.

Каждая запись схемы сообщений имеет следующий вид:

_Уведомление_ об\_ **(** _ID_, _мемберфксн_ **)**

где `id` указывает идентификатор дочернего окна элемента управления, отправляющего уведомление, а `memberFxn` — имя родительской функции-члена, которая была написана для работы с уведомлением.

Прототип родительской функции выглядит следующим образом:

`afx_msg void memberFxn();`

Существует только одна запись схемы сообщений, относящаяся только к `CCheckListBox` (а также записи схемы сообщений для [CListBox](../../mfc/reference/clistbox-class.md)):

- ON_CLBN_CHKCHANGE пользователь изменил состояние флажка элемента.

Если поле контрольного списка является полем контрольного списка по умолчанию (список строк с флажками по умолчанию слева от каждой), можно использовать Кчекклистбокс по умолчанию [::D равитем](#drawitem) , чтобы нарисовать поле контрольного списка. В противном случае необходимо переопределить функции [CListBox:: компареитем](../../mfc/reference/clistbox-class.md#compareitem) и [Кчекклистбокс::D равитем](#drawitem) и [кчекклистбокс:: меасуреитем](#measureitem) .

Вы можете создать поле контрольного списка либо из шаблона диалогового окна, либо непосредственно в коде.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cchecklistbox"></a>Кчекклистбокс:: Кчекклистбокс

Формирует объект `CCheckListBox`.

```
CCheckListBox();
```

### <a name="remarks"></a>Remarks

Объект `CCheckListBox` создается в два этапа. Сначала определите класс, производный от `CCheckListBox`, затем вызовите `Create`, который инициализирует окно контрольного списка Windows и присоединяет его к объекту `CCheckListBox`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>Кчекклистбокс:: Create

Создает окно контрольного списка Windows и прикрепляет его к объекту `CCheckListBox`.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль поля контрольного списка. Стиль должен быть LBS_HASSTRINGS и либо LBS_OWNERDRAWFIXED (все элементы в списке имеют одинаковую высоту), либо LBS_OWNERDRAWVARIABLE (элементы в списке имеют различные значения высоты). Этот стиль можно сочетать с другими [стилями списка](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) , кроме LBS_USETABSTOPS.

*rect*<br/>
Задает размер и расположение поля контрольного списка. Может быть либо объектом [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структурой [Rect](/windows/win32/api/windef/ns-windef-rect) .

*ппарентвнд*<br/>
Указывает родительское окно поля контрольного списка (обычно объект `CDialog`). Оно не должно иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления поля контрольного списка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Объект `CCheckListBox` создается в два этапа. Сначала определите класс, производный от `CcheckListBox`, а затем вызовите `Create`, который инициализирует окно контрольного списка Windows и прикрепляет его к `CCheckListBox`. Пример см. в разделе [кчекклистбокс:: кчекклистбокс](#cchecklistbox) .

Когда `Create` выполняется, Windows отправляет в элемент управления "контрольный список" [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщения.

Эти сообщения по умолчанию обрабатываются функциями члена [оннккреате](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [оннккалксизе](../../mfc/reference/cwnd-class.md#onnccalcsize)и [онжетминмаксинфо](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) в базовом классе `CWnd`. Чтобы расширить обработку сообщений по умолчанию, добавьте к производному классу схему сообщения и переопределите предыдущие функции-члены обработчика сообщений. Переопределите `OnCreate`, например, чтобы выполнить необходимую инициализацию для нового класса.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления "контрольный список":

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

- WS_VSCROLL добавить вертикальную полосу прокрутки

- WS_HSCROLL добавить горизонтальную полосу прокрутки

- WS_GROUP к группам элементов управления

- WS_TABSTOP разрешить переход к этому элементу управления

##  <a name="drawitem"></a>Кчекклистбокс::D Равитем

Вызывается структурой при изменении визуального аспекта отображаемого владельцем поля контрольного списка.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Длинный указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , содержащую сведения о типе требуемой прорисовки.

### <a name="remarks"></a>Remarks

Элементы `itemAction` и `itemState` структуры `DRAWITEMSTRUCT` определяют выполняемое действие рисования.

По умолчанию эта функция рисует список флажков по умолчанию, состоящий из списка строк, для каждого из которых установлен флажок Размер по умолчанию слева. Размер списка флажков указан в поле [создать](#create).

Переопределите эту функцию-член, чтобы реализовать Рисование полей контрольного списка, которые не являются стандартными, например поля контрольных списков со списками, которые не являются строками, с элементами переменной высоты или с флажками, которые не отображаются слева. Приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт* перед завершением этой функции-члена.

Если элементы поля контрольного списка имеют не ту же высоту, стиль поля контрольного списка (указанный в `Create`) должен быть **LBS_OWNERVARIABLE**и необходимо переопределить функцию [меасуреитем](#measureitem) .

##  <a name="enable"></a>Кчекклистбокс:: enable

Вызовите эту функцию, чтобы включить или отключить элемент поля контрольного списка.

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс элемента поля контрольного списка, который должен быть включен.

*бенаблед*<br/>
Указывает, включен ли элемент или отключен.

##  <a name="getcheck"></a>Кчекклистбокс:: Check

Получает состояние указанного флажка.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый от нуля индекс флажка, содержащегося в списке.

### <a name="return-value"></a>Возвращаемое значение

Состояние указанного флажка. В следующей таблице перечислены возможные значения.

|Значение|Description|
|-----------|-----------------|
|BST_CHECKED|Флажок установлен.|
|BST_UNCHECKED|Флажок не установлен.|
|BST_INDETERMINATE|Состояние флажка — неопределенное.|

##  <a name="getcheckstyle"></a>Кчекклистбокс:: Жетчеккстиле

Вызовите эту функцию, чтобы получить стиль поля контрольного списка.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Возвращаемое значение

Стиль флажков элемента управления.

### <a name="remarks"></a>Remarks

Сведения о возможных стилях см. в разделе [сетчеккстиле](#setcheckstyle).

##  <a name="isenabled"></a>Кчекклистбокс:: enable

Вызовите эту функцию, чтобы определить, включен ли элемент.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент включен; в противном случае — 0.

##  <a name="measureitem"></a>Кчекклистбокс:: Меасуреитем

Вызывается структурой при создании поля контрольного списка с стилем, не заданным по умолчанию.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*лпмеасуреитемструкт*<br/>
Длинный указатель на структуру [меасуреитемструкт](/windows/win32/api/winuser/ns-winuser-measureitemstruct) .

### <a name="remarks"></a>Remarks

По умолчанию эта функция члена не выполняет никаких действий. Переопределите эту функцию-член и заполните структуру `MEASUREITEMSTRUCT`, чтобы информировать окна измерений элементов контрольного списка. Если поле контрольного списка создается с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стилем, платформа вызывает эту функцию-член для каждого элемента в списке. В противном случае этот член вызывается только один раз.

##  <a name="ongetcheckposition"></a>Кчекклистбокс:: Онжетчеккпоситион

Платформа вызывает эту функцию для получения позиции и размера флажка в элементе.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>Параметры

*ректитем*<br/>
Позиция и размер элемента списка.

*ректчеккбокс*<br/>
Позиция и размер флажка по умолчанию для элемента.

### <a name="return-value"></a>Возвращаемое значение

Позиция и размер флажка элемента.

### <a name="remarks"></a>Remarks

Реализация по умолчанию возвращает только расположение и размер флажка по умолчанию (`rectCheckBox`). По умолчанию флажок выдается в левом верхнем углу элемента и является стандартным размером флажка. Возможны случаи, когда требуется установить флажки справа или увеличить или уменьшить. В этих случаях Переопределите `OnGetCheckPosition`, чтобы изменить позицию и размер флажка в элементе.

##  <a name="setcheck"></a>Кчекклистбокс:: Сетчекк

Задает состояние указанного флажка.

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый от нуля индекс флажка, содержащегося в списке.

*nДополнительные*<br/>
Состояние кнопки для указанного флажка. Возможные значения см. в разделе "Примечания".

### <a name="remarks"></a>Remarks

В следующей таблице перечислены возможные значения для параметра *nДополнительные* .

|Значение|Description|
|-----------|-----------------|
|BST_CHECKED|Установите флажок.|
|BST_UNCHECKED|Снимите указанный флажок.|
|BST_INDETERMINATE|Установить для указанного состояния флажка значение "неопределенное".<br /><br /> Это состояние доступно только в том случае, если установлен стиль флажка BS_AUTO3STATE или BS_3STATE. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).|

##  <a name="setcheckstyle"></a>Кчекклистбокс:: Сетчеккстиле

Вызовите эту функцию, чтобы установить стиль флажков в окне контрольного списка.

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*нстиле*<br/>
Определяет стиль флажков в окне контрольного списка.

### <a name="remarks"></a>Remarks

Допустимые стили:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

Дополнительные сведения об этих стилях см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).

## <a name="see-also"></a>См. также раздел

[Пример ТСТКОН для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)
