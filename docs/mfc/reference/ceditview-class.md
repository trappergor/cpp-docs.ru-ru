---
title: Класс CEditView
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: e853a770dd1f98b1e7f06afd814962f3b3805ceb
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53177879"
---
# <a name="ceditview-class"></a>Класс CEditView

Тип класса представления, который предоставляет функциональные возможности элемента управления "поле ввода" Windows и может использоваться для реализации простой функциональности текстового редактора.

## <a name="syntax"></a>Синтаксис

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CEditView::CEditView](#ceditview)|Создает объект типа `CEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CEditView::FindText](#findtext)|Поиск строки в тексте.|
|[CEditView::GetBufferLength](#getbufferlength)|Получает длину буфера знаков.|
|[CEditView::GetEditCtrl](#geteditctrl)|Предоставляет доступ к `CEdit` часть `CEditView` объекта (Windows редактирование элемента управления).|
|[CEditView::GetPrinterFont](#getprinterfont)|Извлекает текущий шрифт принтера.|
|[CEditView::GetSelectedText](#getselectedtext)|Извлекает текущее выделение текста.|
|[CEditView::LockBuffer](#lockbuffer)|Блокирует буфер.|
|[CEditView::PrintInsideRect](#printinsiderect)|Отображает текст внутри заданного прямоугольника.|
|[CEditView::SerializeRaw](#serializeraw)|Сериализует `CEditView` объекта на диск в виде текста.|
|[CEditView::SetPrinterFont](#setprinterfont)|Задает новый шрифт принтера.|
|[CEditView::SetTabStops](#settabstops)|Задает позиции табуляции для отображения и печати.|
|[CEditView::UnlockBuffer](#unlockbuffer)|Разблокирует буфер.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CEditView::OnFindNext](#onfindnext)|Находит следующее вхождение строки текста.|
|[CEditView::OnReplaceAll](#onreplaceall)|Заменяет все вхождения заданной строки новую строку.|
|[CEditView::OnReplaceSel](#onreplacesel)|Заменяет текущее выделение.|
|[CEditView::OnTextNotFound](#ontextnotfound)|Вызывается, когда не удается сопоставить любой текст, дополнительные операции поиска.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CEditView::dwStyleDefault](#dwstyledefault)|По умолчанию стиль для объектов типа `CEditView`.|

## <a name="remarks"></a>Примечания

`CEditView` Класс предоставляет следующие дополнительные функции:

- Печать.

- Поиск и замена.

Так как класс `CEditView` является производным от класса `CView`, объекты класса `CEditView` может использоваться с документами и шаблонами документов.

Каждый `CEditView` текст элемента управления сохраняется в свой собственный объект глобальной памяти. Приложение может иметь любое количество `CEditView` объектов.

Создание объекта типа `CEditView` окна редактирования с добавленной функцией, перечисленных выше, или если требуется использовать возможности простого текстового редактора. Объект `CEditView` объект может находиться всей клиентской области окна. Создавать собственные производные классы от `CEditView` добавлять или изменять основные функциональные возможности, или для объявления классов, которые могут быть добавлены в шаблон документа.

Реализация по умолчанию класса `CEditView` обрабатывает следующие команды: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT и ID_FILE_PRINT.

Максимальное количество знаков по умолчанию для `CEditView` является (1024 \* 1024-1 = 1048575). Это можно изменить путем вызова функции EM_LIMITTEXT базового элемента управления edit. Однако ограничения различаются в зависимости от операционной системы и тип элемента управления edit (одинарную или многострочный). Дополнительные сведения об этих ограничениях см. в разделе [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext).

Чтобы изменить это ограничение в элементе управления, переопределите `OnCreate()` работать для вашего `CEditView` класса и вставьте следующую строку кода:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Объекты типа `CEditView` (или типов, производных от `CEditView`) имеют следующие ограничения:

- `CEditView` не реализует true что видишь, то и получаете редактирования (WYSIWYG). Там, где есть выбор между читаемость на экране и сопоставления печатаемых `CEditView` opts для удобства чтения с экрана.

- `CEditView` для отображения текста в только один шрифт. Форматирование специальных символов не поддерживается. См. в разделе класса [CRichEditView](../../mfc/reference/cricheditview-class.md) больше возможностей.

- Объем текста `CEditView` может содержать ограничено. Эти ограничения действуют так же, как `CEdit` элемента управления.

Дополнительные сведения о `CEditView`, см. в разделе [производным представление классов доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="ceditview"></a>  CEditView::CEditView

Создает объект типа `CEditView`.

```
CEditView();
```

### <a name="remarks"></a>Примечания

После создания объекта, необходимо вызвать [CWnd::Create](../../mfc/reference/cwnd-class.md#create) функционировать до использования элемента управления редактирования. Если вы наследуете от класса `CEditView` и добавить его в шаблон с помощью `CWinApp::AddDocTemplate`, как этот конструктор вызывается платформой и `Create` функции.

##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault

Содержит стиль по умолчанию `CEditView` объекта.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Примечания

Передайте этот статический член как *dwStyle* параметр `Create` функцию для получения стиль по умолчанию для `CEditView` объекта.

##  <a name="findtext"></a>  CEditView::FindText

Вызовите `FindText` функции для поиска `CEditView` объекта текстового буфера.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который требуется найти.

*bNext*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска — в конец буфера. Если значение равно FALSE, направление поиска — к началу буфера.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра. Если значение равно TRUE, поиск с учетом регистра. Если значение равно FALSE, поиск не учитывается регистр.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найден искомый текст; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция осуществляет поиск текста в буфере для текст, заданный параметром *lpszFind*, начиная с текущего выделения в направление, заданное параметром *bNext*и с учетом регистра, определяемое *bCase*. Если текст найден, он устанавливает выделение для найденного текста и возвращает ненулевое значение. Если текст не найден, функция возвращает значение 0.

Обычно не нужно вызывать `FindText` функционировать, пока не Переопределите `OnFindNext`, который вызывает `FindText`.

##  <a name="getbufferlength"></a>  CEditView::GetBufferLength

Вызывайте эту функцию члена, чтобы получить число символов в данный момент в буфере редактирования элемента управления, не включая завершающий символ null.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина строки в буфере.

##  <a name="geteditctrl"></a>  CEditView::GetEditCtrl

Вызовите `GetEditCtrl` для получения ссылки в элемент управления редактирования, используемый представлением редактирования.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `CEdit`.

### <a name="remarks"></a>Примечания

Этот элемент управления имеет тип [CEdit](../../mfc/reference/cedit-class.md), поэтому можно управлять напрямую с помощью элемента управления редактирования Windows `CEdit` функций-членов.

> [!CAUTION]
>  С помощью `CEdit` объекта можно изменить состояние базового Windows элемента управления edit. Например, не изменяйте параметры табуляции с помощью [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) работать, поскольку `CEditView` кэширует эти параметры для использования в элементе управления, а также при печати. Вместо этого используйте [CEditView::SetTabStops](#settabstops).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont

Вызовите `GetPrinterFont` для получения указателя на [CFont](../../mfc/reference/cfont-class.md) , описывающий текущий шрифт принтера.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CFont` , указывающий текущий шрифт принтера; Значение NULL, если шрифт принтера не задано. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Примечания

Если шрифт принтера не задано, печати поведение по умолчанию `CEditView` класс-печать с помощью шрифтом, который используется для отображения.

Эта функция используется для определения текущего шрифта принтера. Если это не шрифт нужный принтер, используйте [CEditView::SetPrinterFont](#setprinterfont) для его изменения.

##  <a name="getselectedtext"></a>  CEditView::GetSelectedText

Вызовите `GetSelectedText` Копировать выделенный текст в `CString` объекта до конца строки выделения или знак, перед первым символом возврата каретки в выделении.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Параметры

*strResult*<br/>
Ссылку на `CString` объект, который должен получить выделенный текст.

##  <a name="lockbuffer"></a>  CEditView::LockBuffer

Вызов этой функции-члена для получения указателя на буфер. Не следует изменять буфера.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер элемента управления поля ввода.

##  <a name="onfindnext"></a>  CEditView::OnFindNext

Осуществляет поиск текста в буфере для текст, заданный параметром *lpszFind*, в направление, заданное параметром *bNext*, с учетом регистра, определяемое *bCase*.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который требуется найти.

*bNext*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска — в конец буфера. Если значение равно FALSE, направление поиска — к началу буфера.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра. Если значение равно TRUE, поиск с учетом регистра. Если значение равно FALSE, поиск не учитывается регистр.

### <a name="remarks"></a>Примечания

Поиск начинается с начала текущего выделенного фрагмента и достигается посредством вызова [FindText](#findtext). В реализации по умолчанию `OnFindNext` вызовы [OnTextNotFound](#ontextnotfound) Если текст не найден.

Переопределить `OnFindNext` для изменения способа `CEditView`-производный объект ищет текст. `CEditView` вызовы `OnFindNext` когда пользователь нажимает кнопку Найти далее в стандартное диалоговое окно поиска.

##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll

`CEditView` вызовы `OnReplaceAll` при нажатии кнопки "Заменить все" в стандартное диалоговое окно замены.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который требуется найти.

*lpszReplace*<br/>
Текст, замещающий текст для поиска.

*bCase*<br/>
Указывает, учитывается ли регистр символов поиска. Если значение равно TRUE, поиск с учетом регистра. Если значение равно FALSE, поиск не учитывается регистр.

### <a name="remarks"></a>Примечания

`OnReplaceAll` Осуществляет поиск текста в буфере для текст, заданный параметром *lpszFind*, с учетом регистра, определяемое *bCase*. Поиск начинается с начала текущего выделенного фрагмента. Каждый раз найден искомый текст, эта функция заменяет это вхождение текста, текст, заданный параметром *lpszReplace*. Поиск выполняется с помощью вызова [FindText](#findtext). В реализации по умолчанию [OnTextNotFound](#ontextnotfound) вызывается, если текст не найден.

Если текущее выделение не соответствует *lpszFind*, выделение обновляется до первого вхождения текст, заданный параметром *lpszFind* и заменой не выполняется. Это позволяет пользователю подтвердить, что это нужно делать, если выделение не соответствует заменяемый текст.

Переопределить `OnReplaceAll` для изменения способа `CEditView`-производный объект заменяет текст.

##  <a name="onreplacesel"></a>  CEditView::OnReplaceSel

`CEditView` вызовы `OnReplaceSel` когда пользователь выбирает кнопку «Заменить» в диалоговом окне заменить стандартный.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который требуется найти.

*bNext*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска — в конец буфера. Если значение равно FALSE, направление поиска — к началу буфера.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра. Если значение равно TRUE, поиск с учетом регистра. Если значение равно FALSE, поиск не учитывается регистр.

*lpszReplace*<br/>
Текст заменяется найденный текст.

### <a name="remarks"></a>Примечания

После замены выделение, эта функция осуществляет поиск текста в буфер для следующего вхождения текст, заданный параметром *lpszFind*, в направление, заданное параметром *bNext*, с учетом регистра определяется *bCase*. Поиск выполняется с помощью вызова [FindText](#findtext). Если текст не найден, [OnTextNotFound](#ontextnotfound) вызывается.

Переопределить `OnReplaceSel` для изменения способа `CEditView`-производный объект заменяет выделенный текст.

##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound

Переопределите эту функцию, чтобы изменить реализацию по умолчанию, которая вызывает функцию Windows `MessageBeep`.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который требуется найти.

##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect

Вызовите `PrintInsideRect` печать текста в прямоугольник, определяемый *rectLayout*.

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства принтера.

*rectLayout*<br/>
Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [структура RECT](/windows/desktop/api/windef/ns-windef-tagrect) указание прямоугольник, в котором будет отображаться текст.

*nIndexStart*<br/>
Индекс в буфере для отображения первого символа.

*nIndexStop*<br/>
Индекс в буфере, следующих за последним символом должен быть прорисован символа.

### <a name="return-value"></a>Возвращаемое значение

Индекс следующего символа для печати (то есть символ, следующий к просмотру последнего символа).

### <a name="remarks"></a>Примечания

Если `CEditView` элемент управления не имеет стиль ES_AUTOHSCROLL, текст переносится внутри прямоугольника, подготовки к просмотру. Если элемент управления со стилем ES_AUTOHSCROLL, текст обрезается правого края прямоугольника.

`rect.bottom` Элемент *rectLayout* объекта изменяется таким образом, чтобы измерения прямоугольника определяют часть исходный прямоугольник, который может быть занято текст.

##  <a name="serializeraw"></a>  CEditView::SerializeRaw

Вызовите `SerializeRaw` иметь `CArchive` объекта чтения или записи текста `CEditView` объекта в текстовый файл.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
Ссылка на `CArchive` объект, который хранит сериализованный текст.

### <a name="remarks"></a>Примечания

`SerializeRaw` отличается от `CEditView`на внутреннюю реализацию `Serialize` считывает и записывает только текст, без предшествующих описание объекта данных.

##  <a name="setprinterfont"></a>  CEditView::SetPrinterFont

Вызовите `SetPrinterFont` для установки принтера шрифта для шрифта, указанного *pFont*.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на объект типа `CFont`. Если значение равно NULL, шрифт, используемый для печати основан на шрифт.

### <a name="remarks"></a>Примечания

Если требуется настроить для представления всегда использовать определенный шрифт для печати, включить вызов `SetPrinterFont` в вашем классе `OnPreparePrinting` функции. Это виртуальная функция вызывается перед печатью, поэтому шрифта изменения вступят в силу до печати просмотреть содержимое.

##  <a name="settabstops"></a>  CEditView::SetTabStops

Вызывайте эту функцию, чтобы установить позицию табуляции, используемый для отображения и печати.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Параметры

*nTabStops*<br/>
Ширина каждой позиции табуляции в диалоговых единицах.

### <a name="remarks"></a>Примечания

Поддерживается только один ширину табуляции. ( `CEdit` объекты поддерживают несколько ширину переходов.) Значения ширины, в единицах диалоговое окно, которое равно четверть Средняя ширина символа (с учетом прописных и строчных букв только) шрифта, используемого во время печати или отображения. Не следует использовать `CEdit::SetTabStops` поскольку `CEditView` необходимо кэшировать значение табуляции.

Эта функция изменяет только вкладки объекта, для которого он вызывается. Чтобы изменить на вкладке останавливает для каждого `CEditView` в приложении, следует вызвать каждый объект `SetTabStops` функции.

### <a name="example"></a>Пример

Этот фрагмент кода задает позиции табуляции в элементе управления, чтобы каждый четвертый символ тщательно Измеряя шрифт, который использует элемент управления.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer

Вызовите эту функцию-член для разблокировки буфера.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>Примечания

Вызовите `UnlockBuffer` после завершения использования указатель, возвращенный [LockBuffer](#lockbuffer).

## <a name="see-also"></a>См. также

[Пример MFC SUPERPAD](../../visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
