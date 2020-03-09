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
ms.openlocfilehash: e9b7dea980e607c776e2d50c679042c765080fdb
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78872499"
---
# <a name="ceditview-class"></a>Класс CEditView

Тип класса представления, который предоставляет функциональные возможности элемента управления "поле ввода" Windows и может использоваться для реализации простой функциональности текстового редактора.

## <a name="syntax"></a>Синтаксис

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CEditView:: CEditView](#ceditview)|Создает объект типа `CEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CEditView:: строки FindText](#findtext)|Выполняет поиск строки внутри текста.|
|[CEditView:: Жетбуфферленгс](#getbufferlength)|Получает длину символьного буфера.|
|[CEditView:: Жетедитктрл](#geteditctrl)|Предоставляет доступ к `CEdit` части объекта `CEditView` (элемент управления Windows Edit).|
|[CEditView:: Жетпринтерфонт](#getprinterfont)|Извлекает текущий шрифт принтера.|
|[CEditView:: Жетселектедтекст](#getselectedtext)|Извлекает текущий выделенный фрагмент текста.|
|[CEditView:: Локкбуффер](#lockbuffer)|Блокирует буфер.|
|[CEditView::P Ринтинсидерект](#printinsiderect)|Отображает текст внутри данного прямоугольника.|
|[CEditView:: Сериализерав](#serializeraw)|Сериализует объект `CEditView` на диск в виде необработанного текста.|
|[CEditView:: Сетпринтерфонт](#setprinterfont)|Задает новый шрифт принтера.|
|[CEditView:: Сеттабстопс](#settabstops)|Задает позиции табуляции как для экрана, так и для печати.|
|[CEditView:: Унлоккбуффер](#unlockbuffer)|Разблокирует буфер.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[CEditView:: Онфинднекст](#onfindnext)|Находит следующее вхождение текстовой строки.|
|[CEditView:: Онреплацеалл](#onreplaceall)|Заменяет все вхождения заданной строки новой строкой.|
|[CEditView:: Онреплацесел](#onreplacesel)|Заменяет текущий выбор.|
|[CEditView:: Онтекстнотфаунд](#ontextnotfound)|Вызывается, когда операция поиска не может сопоставить какой-либо текст.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[CEditView::d Встиледефаулт](#dwstyledefault)|Стиль по умолчанию для объектов типа `CEditView`.|

## <a name="remarks"></a>Remarks

Класс `CEditView` предоставляет следующие дополнительные функции:

- Печать.

- Поиск и замена.

Поскольку класс `CEditView` является производным от класса `CView`, объекты класса `CEditView` можно использовать с документами и шаблонами документов.

Каждый текст элемента управления `CEditView` хранится в собственном объекте глобальной памяти. Приложение может иметь любое количество `CEditView` объектов.

Создайте объекты типа `CEditView`, если требуется окно редактирования с добавленными функциями, приведенными выше, или если вам нужны функциональные возможности простого текстового редактора. Объект `CEditView` может занимать всю клиентскую область окна. Создайте собственные классы из `CEditView`, чтобы добавить или изменить основные функциональные возможности или объявить классы, которые можно добавить в шаблон документа.

Реализация класса `CEditView` по умолчанию обрабатывает следующие команды: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT и ID_FILE_PRINT.

Предельный размер символов по умолчанию для `CEditView` — (1024 \* 1024-1 = 1048575). Это можно изменить, вызвав функцию EM_LIMITTEXT базового элемента управления Edit. Однако ограничения различаются в зависимости от операционной системы и типа элемента управления "поле ввода" (один или несколько строк). Дополнительные сведения об этих ограничениях см. в разделе [EM_LIMITTEXT](/windows/win32/Controls/em-limittext).

Чтобы изменить это ограничение в элементе управления, переопределите функцию `OnCreate()` для класса `CEditView` и вставьте следующую строку кода:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Объекты типа `CEditView` (или типы, производные от `CEditView`) имеют следующие ограничения.

- `CEditView` не реализует верное значение, которое вы видите при редактировании (WYSIWYG). Там, где имеется возможность выбора между удобочитаемостью на экране и соответствующими печатными выводимыми данными, `CEditView` подойдет для удобочитаемости экрана.

- `CEditView` может отображать текст только в одном шрифте. Специальное форматирование символов не поддерживается. Дополнительные возможности см. в разделе класс [CRichEditView](../../mfc/reference/cricheditview-class.md) .

- Количество текста, которое может содержать `CEditView`, ограничено. Ограничения одинаковы для элемента управления `CEdit`.

Дополнительные сведения о `CEditView`см. [в разделе классы производного представления, доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[кктрлвиев](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Требования

**Заголовок:** афксекст. h

##  <a name="ceditview"></a>CEditView:: CEditView

Создает объект типа `CEditView`.

```
CEditView();
```

### <a name="remarks"></a>Remarks

После создания объекта необходимо вызвать функцию [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) перед использованием элемента управления Edit. Если вы наследуете класс от `CEditView` и добавите его в шаблон с помощью `CWinApp::AddDocTemplate`, платформа вызывает как этот конструктор, так и функцию `Create`.

##  <a name="dwstyledefault"></a>CEditView::d Встиледефаулт

Содержит стиль по умолчанию для объекта `CEditView`.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Remarks

Передайте этот статический член в качестве параметра *двстиле* функции `Create`, чтобы получить стиль по умолчанию для объекта `CEditView`.

##  <a name="findtext"></a>CEditView:: строки FindText

Вызовите функцию `FindText` для поиска в текстовом буфере объекта `CEditView`.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Текст, который необходимо найти.

*бнекст*<br/>
Задает направление поиска. Если значение равно TRUE, направление поиска находится в направлении конца буфера. Если значение равно FALSE, направление поиска находится в направлении начала буфера.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске. Если значение равно TRUE, поиск выполняется с учетом регистра. Если значение равно FALSE, поиск не учитывает регистр.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если искомый текст найден. в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция ищет текст в буфере для текста, указанного параметром *лпсзфинд*, начиная с текущего выбора, в направлении, указанном параметром *бнекст*, и с учетом регистра, заданным параметром *бкасе*. Если текст найден, он устанавливает для выделения найденный текст и возвращает ненулевое значение. Если текст не найден, функция возвращает 0.

Обычно не требуется вызывать функцию `FindText`, если не переопределяете `OnFindNext`, который вызывает `FindText`.

##  <a name="getbufferlength"></a>CEditView:: Жетбуфферленгс

Вызовите эту функцию члена для получения количества символов, находящихся в данный момент в буфере элемента управления правки, не включая знак завершения null.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина строки в буфере.

##  <a name="geteditctrl"></a>CEditView:: Жетедитктрл

Вызовите `GetEditCtrl`, чтобы получить ссылку на элемент управления Edit, используемый представлением редактирования.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект `CEdit`.

### <a name="remarks"></a>Remarks

Этот элемент управления имеет тип [CEdit](../../mfc/reference/cedit-class.md), поэтому вы можете манипулировать элементом управления Windows Edit напрямую, используя функции-члены `CEdit`.

> [!CAUTION]
>  Использование объекта `CEdit` может изменить состояние базового элемента управления "поле ввода Windows". Например, не следует изменять параметры табуляции с помощью функции [CEdit:: сеттабстопс](../../mfc/reference/cedit-class.md#settabstops) , так как `CEditView` кэширует эти параметры для использования как в элементе управления Editing, так и при печати. Вместо этого используйте [CEditView:: сеттабстопс](#settabstops).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>CEditView:: Жетпринтерфонт

Вызовите `GetPrinterFont`, чтобы получить указатель на объект [кфонт](../../mfc/reference/cfont-class.md) , описывающий текущий шрифт принтера.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CFont`, указывающий текущий шрифт принтера. Значение NULL, если шрифт принтера не задан. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Remarks

Если шрифт принтера не задан, то поведение печати по умолчанию класса `CEditView` будет печататься с тем же шрифтом, который использовался для отображения.

Используйте эту функцию, чтобы определить текущий шрифт принтера. Если он не является нужным шрифтом принтера, используйте [CEditView:: сетпринтерфонт](#setprinterfont) , чтобы изменить его.

##  <a name="getselectedtext"></a>CEditView:: Жетселектедтекст

Вызовите `GetSelectedText`, чтобы скопировать выделенный текст в объект `CString`, до конца выделенного фрагмента или символа, предшествующего первому символу возврата каретки в выделенном фрагменте.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Параметры

*стрресулт*<br/>
Ссылка на объект `CString`, который будет принимать выделенный текст.

##  <a name="lockbuffer"></a>CEditView:: Локкбуффер

Вызовите эту функцию-член, чтобы получить указатель на буфер. Буфер не должен изменяться.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер элемента управления редактирования.

##  <a name="onfindnext"></a>CEditView:: Онфинднекст

Ищет текст в буфере для текста, заданного параметром *лпсзфинд*, в направлении, указанном параметром *бнекст*, с учетом регистра, заданным параметром *бкасе*.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Текст, который необходимо найти.

*бнекст*<br/>
Задает направление поиска. Если значение равно TRUE, направление поиска находится в направлении конца буфера. Если значение равно FALSE, направление поиска находится в направлении начала буфера.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске. Если значение равно TRUE, поиск выполняется с учетом регистра. Если значение равно FALSE, поиск не учитывает регистр.

### <a name="remarks"></a>Remarks

Поиск начинается в начале текущего выделения и выполняется посредством вызова [строки FindText](#findtext). В реализации по умолчанию `OnFindNext` вызывает [онтекстнотфаунд](#ontextnotfound) , если текст не найден.

Переопределите `OnFindNext`, чтобы изменить способ поиска в тексте объекта, производного `CEditView`. `CEditView` вызывает `OnFindNext`, когда пользователь нажимает кнопку Найти далее в стандартном диалоговом окне поиска.

##  <a name="onreplaceall"></a>CEditView:: Онреплацеалл

`CEditView` вызывает `OnReplaceAll`, когда пользователь нажимает кнопку Заменить все в стандартном диалоговом окне заменить.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Текст, который необходимо найти.

*лпсзреплаце*<br/>
Текст для замены искомого текста.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске. Если значение равно TRUE, поиск выполняется с учетом регистра. Если значение равно FALSE, поиск не учитывает регистр.

### <a name="remarks"></a>Remarks

`OnReplaceAll` ищет текст в буфере для текста, указанного параметром *лпсзфинд*, с учетом регистра, заданным параметром *бкасе*. Поиск начинается в начале текущего выделения. При каждом обнаружении искомого текста эта функция заменяет вхождение текста текстом, заданным параметром *лпсзреплаце*. Поиск выполняется через вызов [строки FindText](#findtext). В реализации по умолчанию [онтекстнотфаунд](#ontextnotfound) вызывается, если текст не найден.

Если текущий выделенный фрагмент не соответствует *лпсзфинд*, выборка обновляется до первого вхождения текста, указанного в параметре *лпсзфинд* , а замена не выполняется. Это позволяет пользователю подтвердить, что это необходимо сделать, если выбор не соответствует заменяемому тексту.

Переопределите `OnReplaceAll`, чтобы изменить способ замены текста объектом, производным `CEditView`.

##  <a name="onreplacesel"></a>CEditView:: Онреплацесел

`CEditView` вызывает `OnReplaceSel`, когда пользователь нажимает кнопку Заменить в стандартном диалоговом окне замены.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Текст, который необходимо найти.

*бнекст*<br/>
Задает направление поиска. Если значение равно TRUE, направление поиска находится в направлении конца буфера. Если значение равно FALSE, направление поиска находится в направлении начала буфера.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске. Если значение равно TRUE, поиск выполняется с учетом регистра. Если значение равно FALSE, поиск не учитывает регистр.

*лпсзреплаце*<br/>
Текст для замены найденного текста.

### <a name="remarks"></a>Remarks

После замены выделения эта функция ищет следующий текст в буфере для следующего вхождения текста, указанного параметром *лпсзфинд*, в направлении, указанном параметром *бнекст*, с учетом регистра, заданным параметром *бкасе*. Поиск выполняется через вызов [строки FindText](#findtext). Если текст не найден, вызывается [онтекстнотфаунд](#ontextnotfound) .

Переопределите `OnReplaceSel`, чтобы изменить способ, которым объект, производный от `CEditView`, заменит выбранный текст.

##  <a name="ontextnotfound"></a>CEditView:: Онтекстнотфаунд

Переопределите эту функцию, чтобы изменить реализацию по умолчанию, которая вызывает функцию Windows `MessageBeep`.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Текст, который необходимо найти.

##  <a name="printinsiderect"></a>CEditView::P Ринтинсидерект

Вызовите `PrintInsideRect`, чтобы напечатать текст в прямоугольнике, указанном параметром *ректлайаут*.

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

*ректлайаут*<br/>
Ссылка на объект [крект](../../atl-mfc-shared/reference/crect-class.md) или [структуру Rect](/windows/win32/api/windef/ns-windef-rect) , указывающую прямоугольник, в котором должен быть визуализирован текст.

*ниндексстарт*<br/>
Индекс в буфере первого отображаемого символа.

*ниндексстоп*<br/>
Индекс в буфере символа, следующего за последним символом для подготовки к просмотру.

### <a name="return-value"></a>Возвращаемое значение

Индекс следующего печатаемого символа (то есть символа после последнего отрисованного символа).

### <a name="remarks"></a>Remarks

Если элемент управления `CEditView` не имеет стиля ES_AUTOHSCROLL, текст упаковывается в прямоугольник отрисовки. Если элемент управления имеет стиль ES_AUTOHSCROLL, текст обрезается по правому краю прямоугольника.

Элемент `rect.bottom` объекта *ректлайаут* изменяется таким образом, чтобы размеры прямоугольника определяли часть исходного прямоугольника, занятого текстом.

##  <a name="serializeraw"></a>CEditView:: Сериализерав

Вызовите `SerializeRaw`, чтобы объект `CArchive` читал или записал текст в объект `CEditView` в текстовый файл.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
Ссылка на объект `CArchive`, в котором хранится сериализованный текст.

### <a name="remarks"></a>Remarks

`SerializeRaw` отличается от внутренней реализации `CEditView``Serialize` в том, что он считывает и записывает только текст без предшествующих данных описания объекта.

##  <a name="setprinterfont"></a>CEditView:: Сетпринтерфонт

Вызовите `SetPrinterFont`, чтобы установить шрифт принтера на шрифт, заданный параметром *пфонт*.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Параметры

*пфонт*<br/>
Указатель на объект типа `CFont`. Если значение равно NULL, шрифт, используемый для печати, основан на отображаемом шрифте.

### <a name="remarks"></a>Remarks

Если вы хотите, чтобы в представлении всегда использовался определенный шрифт для печати, включите вызов `SetPrinterFont` в функции `OnPreparePrinting` класса. Эта виртуальная функция вызывается перед печатью, поэтому изменение шрифта происходит до вывода содержимого представления.

##  <a name="settabstops"></a>CEditView:: Сеттабстопс

Вызовите эту функцию, чтобы задать позиции табуляции, используемые для вывода и печати.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Параметры

*нтабстопс*<br/>
Ширина каждой позиции табуляции в диалоговых единицах.

### <a name="remarks"></a>Remarks

Поддерживается только одна ширина табуляции. (`CEdit` объекты поддерживают несколько заданной ширины табуляции.) Значения ширины находятся в единицах диалогового окна, которые равны одной четверти от средней ширины символов (только для символов верхнего и нижнего регистра) шрифта, используемого во время печати или отображения. Не следует использовать `CEdit::SetTabStops`, поскольку `CEditView` должны кэшировать значение табуляции TAB.

Эта функция изменяет только вкладки объекта, для которого она вызывается. Чтобы изменить позиции табуляции для каждого объекта `CEditView` в приложении, вызовите функцию `SetTabStops` каждого объекта.

### <a name="example"></a>Пример

Этот фрагмент кода задает позиции табуляции в элементе управления на каждый четвертый символ, аккуратно измеряя шрифт, используемый элементом управления.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>CEditView:: Унлоккбуффер

Вызовите эту функцию члена, чтобы разблокировать буфер.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>Remarks

Вызовите `UnlockBuffer` после завершения использования указателя, возвращенного [локкбуффер](#lockbuffer).

## <a name="see-also"></a>См. также раздел

[Пример SUPERPAD в MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
