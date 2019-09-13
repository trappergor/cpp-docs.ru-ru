---
title: Класс CRichEditView
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: b32578cc3c9ad4f7a89b8ee76449259c0fa0b43b
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741513"
---
# <a name="cricheditview-class"></a>Класс CRichEditView

С помощью [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) и [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md)предоставляет функциональные возможности элемента управления Rich Edit в контексте архитектуры представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CRichEditView:: CRichEditView](#cricheditview)|Создает объект `CRichEditView`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CRichEditView:: Аджустдиалогпоситион](#adjustdialogposition)|Перемещает диалоговое окно, чтобы оно не скрывало текущее выделение.|
|[CRichEditView:: Канпасте](#canpaste)|Указывает, содержит ли буфер обмена данные, которые могут быть вставлены в представление с расширенными возможностями редактирования.|
|[CRichEditView::D Опасте](#dopaste)|Вставляет элемент OLE в это представление расширенного редактирования.|
|[CRichEditView:: строки FindText](#findtext)|Находит указанный текст, вызывая курсор ожидания.|
|[CRichEditView:: Финдтекстсимпле](#findtextsimple)|Находит указанный текст.|
|[CRichEditView:: Жетчарформатселектион](#getcharformatselection)|Извлекает атрибуты форматирования символов для текущего выделения.|
|[CRichEditView:: a Document](#getdocument)|Извлекает указатель на связанный [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|
|[CRichEditView:: Жетинплацеактивеитем](#getinplaceactiveitem)|Извлекает элемент OLE, который находится в данный момент в режиме расширенного редактирования.|
|[Поля CRichEditView:: Margin](#getmargins)|Извлекает поля для этого представления расширенного редактирования.|
|[CRichEditView:: Жетпажерект](#getpagerect)|Извлекает прямоугольник страницы для этого представления расширенного редактирования.|
|[CRichEditView:: Жетпаперсизе](#getpapersize)|Извлекает размер бумаги для этого представления расширенного редактирования.|
|[CRichEditView:: Жетпараформатселектион](#getparaformatselection)|Извлекает атрибуты форматирования абзаца для текущего выделения.|
|[CRichEditView:: Жетпринтрект](#getprintrect)|Извлекает прямоугольник печати для этого представления расширенного редактирования.|
|[CRichEditView:: Жетпринтвидс](#getprintwidth)|Получает ширину печати для этого представления расширенного редактирования.|
|[CRichEditView:: Жетричедитктрл](#getricheditctrl)|Извлекает элемент управления Rich Edit.|
|[CRichEditView:: Жетселектедитем](#getselecteditem)|Извлекает выбранный элемент из представления форматированного ввода.|
|[CRichEditView:: Жеттекстленгс](#gettextlength)|Извлекает длину текста в режиме форматированного редактирования.|
|[CRichEditView:: Жеттекстленгсекс](#gettextlengthex)|Извлекает количество символов или байтов в представлении с расширенным редактированием. Расширенный список флагов для метода определения длины.|
|[CRichEditView:: Инсертфилеасобжект](#insertfileasobject)|Вставляет файл как элемент OLE.|
|[CRichEditView:: InsertItem](#insertitem)|Вставляет новый элемент как элемент OLE.|
|[CRichEditView:: Исричедитформат](#isricheditformat)|Указывает, содержит ли буфер обмена данные в формате редактирования или текста.|
|[CRichEditView:: Ончареффект](#onchareffect)|Переключает форматирование символов для текущего выделенного фрагмента.|
|[CRichEditView:: Онпараалигн](#onparaalign)|Изменяет выравнивание абзацев.|
|[CRichEditView:: Онупдатечареффект](#onupdatechareffect)|Обновляет пользовательский интерфейс команды для общих функций элементов.|
|[CRichEditView:: Онупдатепараалигн](#onupdateparaalign)|Обновляет пользовательский интерфейс команды для открытых функций элементов в абзаце.|
|[CRichEditView::P Ринтинсидерект](#printinsiderect)|Форматирует указанный текст в пределах данного прямоугольника.|
|[CRichEditView::P Ринтпаже](#printpage)|Форматирует указанный текст на данной странице.|
|[CRichEditView:: Сетчарформат](#setcharformat)|Задает атрибуты форматирования символов для текущего выделения.|
|[CRichEditView:: Сетмаргинс](#setmargins)|Задает поля для этого представления расширенного редактирования.|
|[CRichEditView:: Сетпаперсизе](#setpapersize)|Задает размер бумаги для этого представления расширенного редактирования.|
|[CRichEditView:: Сетпараформат](#setparaformat)|Задает атрибуты форматирования абзаца для текущего выделения.|
|[CRichEditView:: Текстнотфаунд](#textnotfound)|Сбрасывает состояние внутреннего поиска элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CRichEditView:: Жетклипбоарддата](#getclipboarddata)|Извлекает объект буфера обмена для диапазона в этом представлении с расширенным изменением.|
|[CRichEditView:: ContextMenu](#getcontextmenu)|Получает контекстное меню для использования при нажатии правой кнопки мыши.|
|[CRichEditView:: SELECT](#isselected)|Указывает, выбран ли данный элемент OLE.|
|[CRichEditView:: Онфинднекст](#onfindnext)|Находит следующее вхождение подстроки.|
|[CRichEditView:: Онинитиалупдате](#oninitialupdate)|Обновляет представление при первом присоединении к документу.|
|[CRichEditView:: Онпастенативеобжект](#onpastenativeobject)|Получает собственные данные из элемента OLE.|
|[CRichEditView:: Онпринтерчанжед](#onprinterchanged)|Задает характеристики печати для заданного устройства.|
|[CRichEditView:: Онреплацеалл](#onreplaceall)|Заменяет все вхождения заданной строки новой строкой.|
|[CRichEditView:: Онреплацесел](#onreplacesel)|Заменяет текущее выделение.|
|[CRichEditView:: Онтекстнотфаунд](#ontextnotfound)|Обрабатывает уведомление пользователя о том, что запрошенный текст не найден.|
|[CRichEditView:: Куерякцептдата](#queryacceptdata)|Запросы для просмотра сведений о данных `IDataObject`в.|
|[CRichEditView:: Врапчанжед](#wrapchanged)|Корректирует целевое устройство вывода для этого представления расширенного редактирования на основе значения `m_nWordWrap`.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CRichEditView:: m_nBulletIndent](#m_nbulletindent)|Указывает величину отступа для списков маркеров.|
|[CRichEditView:: m_nWordWrap](#m_nwordwrap)|Указывает ограничения переноса по словам.|

## <a name="remarks"></a>Примечания

«Форматируемый элемент управления» — это окно, в котором пользователь может вводить и редактировать текст. Тексту можно присвоить форматирование символов и абзацев, а также включить внедренные объекты OLE. Элементы управления Rich Edit предоставляют программный интерфейс для форматирования текста. Однако приложение должно реализовывать любые компоненты пользовательского интерфейса, необходимые для того, чтобы сделать операции форматирования доступными для пользователя.

`CRichEditView`поддерживает текстовую характеристику текста и форматирования текста. `CRichEditDoc`поддерживает список элементов OLE клиента, которые находятся в представлении. `CRichEditCntrItem`предоставляет доступ на стороне контейнера к элементу OLE-клиента.

Этот общий элемент управления Windows (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанные классы) доступен только для программ, работающих под управлением Windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Пример использования представления форматированного редактирования в приложении MFC см. в примере приложения [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[кктрлвиев](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Требования

**Заголовок:** афксрич. h

##  <a name="adjustdialogposition"></a>CRichEditView:: Аджустдиалогпоситион

Вызовите эту функцию, чтобы переместить заданное диалоговое окно, чтобы оно не скрывало текущее выделение.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Параметры

*пдлг*<br/>
Указатель на `CDialog` объект.

##  <a name="canpaste"></a>CRichEditView:: Канпасте

Вызовите эту функцию, чтобы определить, содержит ли буфер обмена сведения, которые могут быть вставлены в это представление расширенного редактирования.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если буфер обмена содержит данные в формате, который может быть принят этим представлением расширенного редактирования. в противном случае — значение 0.

##  <a name="cricheditview"></a>CRichEditView:: CRichEditView

Вызовите эту функцию, чтобы `CRichEditView` создать объект.

```
CRichEditView();
```

##  <a name="dopaste"></a>CRichEditView::D Опасте

Вызовите эту функцию, чтобы вставить элемент OLE в *датаобж* в этот документ или представление с богатыми возможностями редактирования.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Параметры

*датаобж*<br/>
[Коледатаобжект](../../mfc/reference/coledataobject-class.md) , содержащий вставляемые данные.

*CF*<br/>
Нужный формат буфера обмена.

*хметапикт*<br/>
Метафайл, представляющий элемент для вставления.

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию как часть реализации [куерякцептдата](#queryacceptdata)по умолчанию.

Эта функция определяет тип вставки на основе результатов обработчика для специальной вставки. Если *CF* имеет значение 0, то в новом элементе используется текущее представление значка. Если параметр *CF* имеет ненулевое значение, а *ХМЕТАПИКТ* не равен null, то новый элемент использует *хметапикт* для своего представления.

##  <a name="findtext"></a>CRichEditView:: строки FindText

Вызовите эту функцию, чтобы найти указанный текст и установить его в качестве текущего выбора.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Содержит строку для поиска.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске.

*бворд*<br/>
Указывает, должен ли поиск сопоставлять слова целиком, а не части слов.

*бнекст*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска находится в направлении конца буфера. Если значение равно FALSE, направление поиска находится в направлении начала буфера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найден текст *лпсзфинд* . в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция отображает курсор ожидания во время операции поиска.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

##  <a name="findtextsimple"></a>CRichEditView:: Финдтекстсимпле

Вызовите эту функцию, чтобы найти указанный текст и установить его в качестве текущего выбора.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Содержит строку для поиска.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске.

*бворд*<br/>
Указывает, должен ли поиск сопоставлять слова целиком, а не части слов.

*бнекст*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска находится в направлении конца буфера. Если значение равно FALSE, направление поиска находится в направлении начала буфера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найден текст *лпсзфинд* . в противном случае — 0.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: строки FindText](#findtext).

##  <a name="getcharformatselection"></a>CRichEditView:: Жетчарформатселектион

Вызовите эту функцию, чтобы получить атрибуты форматирования символов для текущего выделения.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Возвращаемое значение

Структура [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) , которая содержит атрибуты форматирования символов для текущего выделения.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в описании сообщения [EM_GETCHARFORMAT](/windows/win32/Controls/em-getcharformat) и структуры [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="getclipboarddata"></a>CRichEditView:: Жетклипбоарддата

Платформа вызывает эту функцию как часть обработки [иричедитолекаллбакк:: жетклипбоарддата](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata).

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Параметры

*лпчрг*<br/>
Указатель на структуру [чарранже](/windows/win32/api/richedit/ns-richedit-charrange) , определяющую диапазон символов (и элементов OLE) для копирования в объект данных, указанный параметром *лплпдатаобж*.

*двреко*<br/>
Флаг операции буфера обмена. Может принимать одно из следующих значений.

- RECO_COPY копировать в буфер обмена.

- RECO_CUT вырезать в буфер обмена.

- Операция перетаскивания RECO_DRAG (перетаскивание).

- Операция удаления RECO_DROP (перетаскивание).

- RECO_PASTE вставка из буфера обмена.

*лпричдатаобж*<br/>
Указатель на объект [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) , содержащий данные буфера обмена из элемента управления Rich Edit ( [Иричедитоле:: жетклипбоарддата](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata)).

*лплпдатаобж*<br/>
Указатель на переменную указателя, которая получает адрес `IDataObject` объекта, представляющего диапазон, указанный в параметре *лпчрг* . Значение *лплпдатаобж* игнорируется, если возвращается ошибка.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, сообщающее об успешном выполнении операции. Дополнительные сведения о HRESULT см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="remarks"></a>Примечания

Если возвращаемое значение указывает на успешное выполнение `IDataObject` , `IRichEditOleCallback::GetClipboardData` возвращает объект, к которому обращается *лплпдатаобж*. в противном случае возвращается объект, к которому обращается *лпричдатаобж*. Переопределите эту функцию для предоставления собственных данных в буфере обмена. Реализация по умолчанию этой функции возвращает значение E_NOTIMPL.

Это расширенный переопределяемый объект.

Дополнительные сведения см. в разделе [иричедитоле:: жетклипбоарддата](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata), [Иричедитолекаллбакк:: жетклипбоарддата](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)и [чарранже](/windows/win32/api/richedit/ns-richedit-charrange) в Windows SDK и см. в разделе [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) в Windows SDK.

##  <a name="getcontextmenu"></a>CRichEditView:: ContextMenu

Платформа вызывает эту функцию как часть обработки [иричедитолекаллбакк:: ContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu).

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Параметры

*селтип*<br/>
Тип выбора. Значения типа выбора описаны в разделе "Примечания".

*лполеобж*<br/>
Указатель на `OLEOBJECT` структуру, указывающую первый выбранный объект OLE, если выделенный фрагмент содержит один или несколько элементов OLE. Если выделение не содержит элементов, *лполеобж* имеет значение null. `OLEOBJECT` Структура содержит указатель на таблицу v-table объекта OLE.

*лпчрг*<br/>
Указатель на структуру [чарранже](/windows/win32/api/richedit/ns-richedit-charrange) , содержащую текущее выделение.

### <a name="return-value"></a>Возвращаемое значение

Обработайте с контекстным меню.

### <a name="remarks"></a>Примечания

Эта функция является типичной частью обработки правой кнопки мыши.

Тип выбора может быть любым сочетанием следующих флагов:

- SEL_EMPTY указывает на отсутствие текущего выбора.

- SEL_TEXT указывает, что текущий выделенный фрагмент содержит текст.

- SEL_OBJECT указывает, что текущий выделенный фрагмент содержит по крайней мере один элемент OLE.

- SEL_MULTICHAR указывает, что текущее выделение содержит более одного символа текста.

- SEL_MULTIOBJECT указывает, что текущее выделение содержит более одного объекта OLE.

Реализация по умолчанию возвращает значение NULL. Это расширенный переопределяемый объект.

Дополнительные сведения см. в разделе [IRichEditOleCallback::GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu) и [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) в Windows SDK.

##  <a name="getdocument"></a>CRichEditView:: a Document

Вызовите эту функцию, чтобы получить указатель на `CRichEditDoc` объект, связанный с этим представлением.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) , связанный с `CRichEditView` объектом.

##  <a name="getinplaceactiveitem"></a>CRichEditView:: Жетинплацеактивеитем

Вызовите эту функцию, чтобы получить объект OLE, который в данный момент активируется `CRichEditView` в этом объекте.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на единичный активный объект [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md) в этом представлении расширенного редактирования; Значение NULL, если в настоящий момент нет объекта OLE в активном состоянии "на месте".

##  <a name="getmargins"></a>Поля CRichEditView:: Margin

Вызовите эту функцию, чтобы получить текущие поля, используемые при печати.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Возвращаемое значение

Поля, используемые при печати, измеряются в MM_TWIPS.

##  <a name="getpagerect"></a>CRichEditView:: Жетпажерект

Вызовите эту функцию, чтобы получить размеры страницы, используемой при печати.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Границы страницы, используемой при печати, измеряется в MM_TWIPS.

### <a name="remarks"></a>Примечания

Это значение основано на размере бумаги.

##  <a name="getpapersize"></a>CRichEditView:: Жетпаперсизе

Вызовите эту функцию, чтобы получить текущий размер бумаги.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер бумаги, используемой при печати, измеряется в MM_TWIPS.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

##  <a name="getparaformatselection"></a>CRichEditView:: Жетпараформатселектион

Вызовите эту функцию, чтобы получить атрибуты форматирования абзаца для текущего выделения.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Возвращаемое значение

Структура [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) , которая содержит атрибуты форматирования абзаца для текущего выделения.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_GETPARAFORMAT](/windows/win32/Controls/em-getparaformat) Message и [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) Structure статьи Windows SDK.

##  <a name="getprintrect"></a>CRichEditView:: Жетпринтрект

Вызовите эту функцию, чтобы получить границы области печати внутри прямоугольника страницы.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Границы области изображения, используемой при печати, измеряется в MM_TWIPS.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

##  <a name="getprintwidth"></a>CRichEditView:: Жетпринтвидс

Вызовите эту функцию, чтобы определить ширину области печати.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина области печати, измеряемая в MM_TWIPS.

##  <a name="getricheditctrl"></a>CRichEditView:: Жетричедитктрл

Вызовите эту функцию, чтобы получить объект [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) , связанный `CRichEditView` с объектом.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

`CRichEditCtrl` Объект для этого представления.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: строки FindText](#findtext).

##  <a name="getselecteditem"></a>CRichEditView:: Жетселектедитем

Вызовите эту функцию для получения `CRichEditCntrItem` объекта OLE (объект), выбранного в данный момент в этом `CRichEditView` объекте.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md) , выбранный в `CRichEditView` объекте; NULL, если в этом представлении не выбран ни один элемент.

##  <a name="gettextlength"></a>CRichEditView:: Жеттекстленгс

Вызовите эту функцию, чтобы получить длину текста в этом `CRichEditView` объекте.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина текста в этом `CRichEditView` объекте.

##  <a name="gettextlengthex"></a>CRichEditView:: Жеттекстленгсекс

Вызовите эту функцию члена, чтобы вычислить длину текста в `CRichEditView` этом объекте.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Значение, указывающее метод, используемый для определения длины текста. Этот элемент может быть одним или несколькими значениями, перечисленными в элементе flags элемента [жеттекстленгсекс](/windows/win32/api/richedit/ns-richedit-gettextlengthex) , описанным в Windows SDK.

*укодепаже*<br/>
Кодовая страница для перевода (CP_ACP для кодовой страницы ANSI, 1200 для Юникода).

### <a name="return-value"></a>Возвращаемое значение

Число символов или байтов в элементе управления "поле ввода". Если в *dwFlags*заданы несовместимые флаги, эта функция члена возвращает E_INVALIDARG.

### <a name="remarks"></a>Примечания

`GetTextLengthEx`предоставляет дополнительные способы определения длины текста. Он поддерживает широкие возможности редактирования 2,0. Дополнительные сведения см. в разделе [об элементах управления Rich Edit](/windows/win32/Controls/about-rich-edit-controls) в Windows SDK.

##  <a name="insertfileasobject"></a>CRichEditView:: Инсертфилеасобжект

Вызовите эту функцию, чтобы вставить указанный файл (в виде объекта [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md) ) в представление с расширенными возможностями редактирования.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Параметры

*лпсзфиленаме*<br/>
Строка, содержащая имя вставляемого файла.

##  <a name="insertitem"></a>CRichEditView:: InsertItem

Вызовите эту функцию, чтобы вставить объект [кричедиткнтритем](../../mfc/reference/cricheditcntritem-class.md) в представление с расширенными возможностями редактирования.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указатель на вставляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее на успешность вставки.

### <a name="remarks"></a>Примечания

Дополнительные сведения о HRESULT см. в разделе [структура кодов ошибок COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

##  <a name="isricheditformat"></a>CRichEditView:: Исричедитформат

Вызовите эту функцию, чтобы определить, является ли *CF* форматом буфера обмена, который является текстовым, форматированным текстом или форматированным текстом с элементами OLE.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Интересующий формат буфера обмена.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если *CF* имеет форматированный формат или текстовый буфер обмена.

##  <a name="isselected"></a>CRichEditView:: SELECT

Вызовите эту функцию, чтобы определить, выбран ли в данном представлении указанный элемент OLE.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Параметры

*пдоЦитем*<br/>
Указатель на объект в представлении.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект выбран. в противном случае — 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если производный класс представления имеет другой метод для обработки выбора элементов OLE.

##  <a name="m_nbulletindent"></a>CRichEditView:: m_nBulletIndent

Отступ для элементов маркированного списка; по умолчанию 720 единиц, то есть 1/2 дюйма.

```
int m_nBulletIndent;
```

##  <a name="m_nwordwrap"></a>CRichEditView:: m_nWordWrap

Указывает тип переноса по словам для этого представления расширенного редактирования.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Примечания

Одно из следующих значений:

- `WrapNone`Указывает, что автоматический перенос по словам отсутствует.

- `WrapToWindow`Обозначает перенос по словам в зависимости от ширины окна.

- `WrapToTargetDevice`Обозначает перенос по словам в зависимости от характеристик целевого устройства.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: врапчанжед](#wrapchanged).

##  <a name="onchareffect"></a>CRichEditView:: Ончареффект

Вызовите эту функцию, чтобы включить эффекты форматирования символов для текущего выделения.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Параметры

*двмаск*<br/>
Эффекты форматирования символов для изменения в текущем выделенном фрагменте.

*двеффект*<br/>
Требуемый список эффектов форматирования символов для переключения.

### <a name="remarks"></a>Примечания

Каждый вызов этой функции переключает указанные эффекты форматирования для текущего выделения.

Дополнительные сведения о параметрах *двмаск* и *двеффект* и их возможностях см. в разделе соответствующие элементы данных [чарформат](/windows/win32/api/richedit/ns-richedit-charformata) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

##  <a name="onfindnext"></a>CRichEditView:: Онфинднекст

Вызывается структурой при обработке команд в диалоговом окне "Найти/заменить".

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Строка, которую надо найти.

*бнекст*<br/>
Направление поиска: Значение TRUE указывает на ненажатие; FALSE, up.

*бкасе*<br/>
Указывает, следует ли учитывать регистр при поиске.

*бворд*<br/>
Указывает, следует ли искать только слова целиком или нет.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для поиска текста в `CRichEditView`. Переопределите эту функцию, чтобы изменить характеристики поиска для производного класса представления.

##  <a name="oninitialupdate"></a>CRichEditView:: Онинитиалупдате

Вызывается структурой после первого присоединения представления к документу, но до первоначального отображения представления.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции вызывает метод [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate) , не содержащий сведений о указаниях (то есть используя значения по умолчанию 0 для параметра *лхинт* и значение NULL для параметра *финт* ). Переопределите эту функцию для выполнения любой однократной инициализации, требующей получения сведений о документе. Например, если приложение имеет документы фиксированного размера, эту функцию можно использовать для инициализации ограничений прокрутки представления в зависимости от размера документа. Если приложение поддерживает документы с переменным размером, используйте `OnUpdate` для обновления ограничений прокрутки при каждом изменении документа.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: m_nWordWrap](#m_nwordwrap).

##  <a name="onpastenativeobject"></a>CRichEditView:: Онпастенативеобжект

Эта функция используется для загрузки собственных данных из внедренного элемента.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Параметры

*лпстг*<br/>
Указатель на объект [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; в противном случае — 0;

### <a name="remarks"></a>Примечания

Как правило, это делается путем создания [колестреамфиле](../../mfc/reference/colestreamfile-class.md) вокруг `IStorage`. Можно присоединить к Archive и [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) , вызываемую для загрузки данных. `COleStreamFile`

Это расширенный переопределяемый объект.

Дополнительные сведения см. в разделе [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) в Windows SDK.

##  <a name="onparaalign"></a>CRichEditView:: Онпараалигн

Вызовите эту функцию, чтобы изменить выравнивание абзаца для выбранных абзацев.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Параметры

*валигн*<br/>
Выравнивание требуемого абзаца. Одно из следующих значений:

- PFA_LEFT выровняйте абзацы по левому краю.

- PFA_RIGHT выровняйте абзацы по правому краю.

- PFA_CENTER выравнивание абзацев между полями.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

##  <a name="onprinterchanged"></a>CRichEditView:: Онпринтерчанжед

Переопределите эту функцию, чтобы изменить характеристики для этого представления форматированного редактирования при изменении принтера.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Параметры

*дкпринтер*<br/>
Объект [CDC](../../mfc/reference/cdc-class.md) для нового принтера.

### <a name="remarks"></a>Примечания

Реализация по умолчанию устанавливает в качестве размера бумаги физическую высоту и ширину для выходного устройства (принтера). Если нет контекста устройства, связанного с *дкпринтер*, реализация по умолчанию устанавливает размер бумаги 8,5 на 11 дюймов.

##  <a name="onreplaceall"></a>CRichEditView:: Онреплацеалл

Вызывается структурой при обработке замены всех команд в диалоговом окне "заменить".

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Заменяемый текст.

*лпсзреплаце*<br/>
Текст для замены.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске.

*бворд*<br/>
Указывает, должны ли в поиске выделяться целые слова.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы заменить все вхождения некоторого заданного текста другой строкой. Переопределите эту функцию, чтобы изменить характеристики поиска для этого представления.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: строки FindText](#findtext).

##  <a name="onreplacesel"></a>CRichEditView:: Онреплацесел

Вызывается структурой при обработке команд Replace в диалоговом окне замены.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Заменяемый текст.

*бнекст*<br/>
Указывает направление поиска: TRUE не работает; FALSE, up.

*бкасе*<br/>
Указывает, учитывается ли регистр при поиске.

*бворд*<br/>
Указывает, должны ли в поиске выделяться целые слова.

*лпсзреплаце*<br/>
Текст для замены.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы заменить одно вхождение некоторого заданного текста другой строкой. Переопределите эту функцию, чтобы изменить характеристики поиска для этого представления.

##  <a name="ontextnotfound"></a>CRichEditView:: Онтекстнотфаунд

Вызывается платформой при сбое поиска.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Текст, который не был найден.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы изменить выходное уведомление из [мессажебип](/windows/win32/api/winuser/nf-winuser-messagebeep).

Дополнительные сведения см. в разделе [мессажебип](/windows/win32/api/winuser/nf-winuser-messagebeep) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

##  <a name="onupdatechareffect"></a>CRichEditView:: Онупдатечареффект

Платформа вызывает эту функцию, чтобы обновить пользовательский интерфейс команды для команд символьных эффектов.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на объект [Поддержка CCmdUI](../../mfc/reference/ccmdui-class.md) .

*двмаск*<br/>
Указывает маску форматирования символов.

*двеффект*<br/>
Указывает результат форматирования символов.

### <a name="remarks"></a>Примечания

Маска *двмаск* указывает, какие атрибуты форматирования символов следует проверять. Флаги *двеффект* список атрибутов форматирования символов, которые нужно задать или очистить.

Дополнительные сведения о параметрах *двмаск* и *двеффект* и их возможностях см. в разделе соответствующие элементы данных [чарформат](/windows/win32/api/richedit/ns-richedit-charformata) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

##  <a name="onupdateparaalign"></a>CRichEditView:: Онупдатепараалигн

Платформа вызывает эту функцию для обновления пользовательского интерфейса команды для команд эффектов абзаца.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на объект [Поддержка CCmdUI](../../mfc/reference/ccmdui-class.md) .

*валигн*<br/>
Выравнивание абзаца для проверки. Одно из следующих значений:

- PFA_LEFT выровняйте абзацы по левому краю.

- PFA_RIGHT выровняйте абзацы по правому краю.

- PFA_CENTER выравнивание абзацев между полями.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

##  <a name="printinsiderect"></a>CRichEditView::P Ринтинсидерект

Вызывайте эту функцию, чтобы отформатировать текст в элементе управления для расширенного редактирования, чтобы оно соответствовало *ректлайаут* для устройства, указанного в *PDC*.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства для области вывода.

*ректлайаут*<br/>
[Rect](/windows/win32/api/windef/ns-windef-rect) или [крект](../../atl-mfc-shared/reference/crect-class.md) , определяющие область вывода.

*ниндексстарт*<br/>
Отсчитываемый от нуля индекс первого форматируемого символа.

*ниндексстоп*<br/>
Отсчитываемый от нуля индекс последнего форматируемого символа.

*баутпут*<br/>
Указывает, должен ли отображаться текст. Значение FALSE показывает, что текст просто измеряется.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа, который помещается в области вывода плюс один.

### <a name="remarks"></a>Примечания

Как правило, за этим вызовом следует вызов [CRichEditCtrl::D исплайбанд](../../mfc/reference/cricheditctrl-class.md#displayband) , который создает выходные данные.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: жетпаперсизе](#getpapersize).

##  <a name="printpage"></a>CRichEditView::P Ринтпаже

Эта функция вызывается для форматирования диапазона текста в элементе управления Rich Edit для устройства вывода, заданного *PDC*.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства для вывода страницы.

*ниндексстарт*<br/>
Отсчитываемый от нуля индекс первого форматируемого символа.

*ниндексстоп*<br/>
Отсчитываемый от нуля индекс последнего форматируемого символа.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа, который помещается на странице плюс один.

### <a name="remarks"></a>Примечания

Макет каждой страницы управляется [жетпажерект](#getpagerect) и [жетпринтрект](#getprintrect). Как правило, за этим вызовом следует вызов [CRichEditCtrl::D исплайбанд](../../mfc/reference/cricheditctrl-class.md#displayband) , который создает выходные данные.

Обратите внимание, что поля задаются относительно физической страницы, а не логической страницы. Таким словами, поля с нуля часто обрезает текст, так как многие принтеры имеют непечатаемые области на странице. Чтобы избежать обрезки текста, следует вызвать [сетмаргинс](#setmargins) и задать разумные поля перед печатью.

##  <a name="queryacceptdata"></a>CRichEditView:: Куерякцептдата

Вызывается платформой для вставки объекта в Расширенное редактирование.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>Параметры

*лпдатаобж*<br/>
Указатель на [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) для запроса.

*лпкфформат*<br/>
Указатель на допустимый формат данных.

*двреко*<br/>
Не используется.

*бреалли*<br/>
Указывает, следует ли продолжать операцию вставки.

*хметафиле*<br/>
Маркер метафайла, используемый для рисования значка элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, сообщающее об успешном выполнении операции.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы она обрабатывала другую организацию COM-элементов в производном классе документа. Это расширенный переопределяемый объект.

Дополнительные сведения о HRESULT и `IDataObject`см. в разделе [структура кодов ошибок com](/windows/win32/com/structure-of-com-error-codes) и [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)соответственно в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

##  <a name="setcharformat"></a>CRichEditView:: Сетчарформат

Вызовите эту функцию, чтобы задать атрибуты форматирования символов для нового текста в `CRichEditView` этом объекте.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Структура [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) , содержащая новые атрибуты форматирования символов по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция изменяет только атрибуты, `dwMask` указанные членом *CF* .

Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](/windows/win32/Controls/em-setcharformat) Message и [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) Structure статьи Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="setmargins"></a>CRichEditView:: Сетмаргинс

Вызовите эту функцию, чтобы задать поля печати для этого представления расширенного редактирования.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Параметры

*ректмаргин*<br/>
Новые значения полей для печати, измеряемые в MM_TWIPS.

### <a name="remarks"></a>Примечания

Если [m_nWordWrap](#m_nwordwrap) имеет `WrapToTargetDevice`значение, необходимо вызвать [врапчанжед](#wrapchanged) после использования этой функции для настройки характеристик печати.

Обратите внимание, что поля, используемые [PrintPage](#printpage) , относительны относительно физической страницы, а не логической страницы. Таким словами, поля с нуля часто обрезает текст, так как многие принтеры имеют непечатаемые области на странице. Чтобы избежать обрезки текста, следует вызвать метод USE `SetMargins` для установки разумных полей принтера перед печатью.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: жетпаперсизе](#getpapersize).

##  <a name="setpapersize"></a>CRichEditView:: Сетпаперсизе

Вызовите эту функцию, чтобы задать размер бумаги для печати этого представления расширенного редактирования.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Параметры

*сизепапер*<br/>
Новые значения размера бумаги для печати, измеряемые в MM_TWIPS.

### <a name="remarks"></a>Примечания

Если [m_nWordWrap](#m_nwordwrap) имеет `WrapToTargetDevice`значение, необходимо вызвать [врапчанжед](#wrapchanged) после использования этой функции для настройки характеристик печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

##  <a name="setparaformat"></a>CRichEditView:: Сетпараформат

Вызывайте эту функцию, чтобы задать атрибуты форматирования абзаца для текущего выделения в `CRichEditView` этом объекте.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Параметры

*pf*<br/>
Структура [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) , содержащая новые атрибуты форматирования абзаца по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Эта функция изменяет только атрибуты, `dwMask` указанные членом *PF* .

Дополнительные сведения см. в разделе [EM_SETPARAFORMAT](/windows/win32/Controls/em-setparaformat) Message и [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) Structure статьи Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

##  <a name="textnotfound"></a>CRichEditView:: Текстнотфаунд

Вызовите эту функцию, чтобы сбросить внутреннее состояние поиска элемента управления [CRichEditView](../../mfc/reference/cricheditview-class.md) после неудачного вызова [строки FindText](#findtext).

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*лпсзфинд*<br/>
Содержит текстовую строку, которая не была найдена.

### <a name="remarks"></a>Примечания

Рекомендуется вызывать этот метод сразу после неудачных вызовов [строки FindText](#findtext) , чтобы внутреннее состояние поиска элемента управления было правильно сброшено.

Параметр *лпсзфинд* должен включать то же содержимое, что и строка, предоставленная для [строки FindText](#findtext). После сброса внутреннего состояния поиска этот метод вызовет метод [онтекстнотфаунд](#ontextnotfound) с указанной строкой поиска.

### <a name="example"></a>Пример

  См. пример для [CRichEditView:: строки FindText](#findtext).

##  <a name="wrapchanged"></a>CRichEditView:: Врапчанжед

Вызывайте эту функцию при изменении характеристик печати ( [сетмаргинс](#setmargins) или [сетпаперсизе](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы изменить способ, которым представление форматированного редактирования будет реагировать на изменения в [m_nWordWrap](#m_nwordwrap) или характеристики печати ( [онпринтерчанжед](#onprinterchanged)).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>См. также

[Образец WORDPAD для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)
