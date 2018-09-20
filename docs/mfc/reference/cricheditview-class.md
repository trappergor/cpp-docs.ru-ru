---
title: Класс CRichEditView | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ca5b649ba5d09d0406658112b8067ed804f7e70
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423940"
---
# <a name="cricheditview-class"></a>Класс CRichEditView

С помощью [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), предоставляет функции элемента управления форматированным редактированием в контексте архитектуры представлений документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRichEditView::CRichEditView](#cricheditview)|Создает объект `CRichEditView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Перемещает диалоговое окно, чтобы он не скрывать текущего выделения.|
|[CRichEditView::CanPaste](#canpaste)|Указывает, содержит ли буфер данных, которая может быть вставлена в представлении rich edit.|
|[CRichEditView::DoPaste](#dopaste)|Вставка элемента OLE в этом представлении rich edit.|
|[CRichEditView::FindText](#findtext)|Выполняет поиск указанного текста, вызов курсор ожидания.|
|[CRichEditView::FindTextSimple](#findtextsimple)|Выполняет поиск указанного текста.|
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Извлекает атрибуты для текущего выделения форматирование символов.|
|[CRichEditView::GetDocument](#getdocument)|Извлекает указатель на связанную [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Извлекает элемент OLE, который является активным в данный момент на месте в представлении rich edit.|
|[CRichEditView::GetMargins](#getmargins)|Возвращает значение поля для этого представления rich edit.|
|[CRichEditView::GetPageRect](#getpagerect)|Извлекает прямоугольник страницы для этого представления rich edit.|
|[CRichEditView::GetPaperSize](#getpapersize)|Извлекает размер бумаги для этого представления rich edit.|
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Извлекает атрибуты для текущего выделения форматирования абзаца.|
|[CRichEditView::GetPrintRect](#getprintrect)|Возвращает прямоугольник, печати, для этого представления rich edit.|
|[CRichEditView::GetPrintWidth](#getprintwidth)|Получает ширину печати для этого представления rich edit.|
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Извлекает элемент управления форматированным редактированием.|
|[CRichEditView::GetSelectedItem](#getselecteditem)|Извлекает выбранный элемент из представления rich edit.|
|[CRichEditView::GetTextLength](#gettextlength)|Получает длину текста в представлении rich edit.|
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Возвращает число символов или байтов, в представлении rich edit. Список развернутой флаг для методом определения длины.|
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Вставляет файл в виде объекта OLE.|
|[CRichEditView::InsertItem](#insertitem)|Вставляет новый элемент в виде объекта OLE.|
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Указывает, содержит ли буфер обмена данные в текстовом формате или форматированным редактированием.|
|[CRichEditView::OnCharEffect](#onchareffect)|Переключает форматирование для текущего выделения символов.|
|[CRichEditView::OnParaAlign](#onparaalign)|Изменение выравнивания абзаца.|
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Обновление пользовательского интерфейса команды для символа открытыми функциями-членами.|
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Обновление пользовательского интерфейса команды для абзаца открытыми функциями-членами.|
|[CRichEditView::PrintInsideRect](#printinsiderect)|Форматирует указанный текст в пределах заданного прямоугольника.|
|[CRichEditView::PrintPage](#printpage)|Форматирует указанный текст в пределах заданной страницы.|
|[CRichEditView::SetCharFormat](#setcharformat)|Задает форматирование атрибутов для текущего выделения символов.|
|[CRichEditView::SetMargins](#setmargins)|Задает поля для этого rich изменить представление.|
|[CRichEditView::SetPaperSize](#setpapersize)|Задает размер бумаги для этого представления rich edit.|
|[CRichEditView::SetParaFormat](#setparaformat)|Задает атрибуты для текущего выделения форматирования абзаца.|
|[CRichEditView::TextNotFound](#textnotfound)|Сбрасывает состояние внутреннего поиска элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CRichEditView::GetClipboardData](#getclipboarddata)|Получает объект Clipboard для диапазона в этом представлении rich edit.|
|[CRichEditView::GetContextMenu](#getcontextmenu)|Получает контекстное меню для использования в правой-нажатия кнопки мыши.|
|[CRichEditView::IsSelected](#isselected)|Указывает, если выбрана заданного объекта OLE, или нет.|
|[CRichEditView::OnFindNext](#onfindnext)|Поиск следующего вхождения подстроки.|
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Обновляет представление при первом прикрепляемые к документу.|
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Получает машинные данные из объекта OLE.|
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Устанавливает параметры печати для заданного устройства.|
|[CRichEditView::OnReplaceAll](#onreplaceall)|Заменяет все вхождения заданной строки новую строку.|
|[CRichEditView::OnReplaceSel](#onreplacesel)|Заменяет текущее выделение.|
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Обрабатывает уведомление пользователя, который не был найден запрошенный текст.|
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Запросы к см. в разделе о данных на `IDataObject`.|
|[CRichEditView::WrapChanged](#wrapchanged)|Настраивает целевое устройство вывода для редактирования этого форматированного текста, представления, основанного на значение `m_nWordWrap`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Указывает отступ для маркированные списки.|
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Указывает ограничения переноса слов.|

## <a name="remarks"></a>Примечания

Управления rich edit «» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматированием символов и абзацев и могут включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.

`CRichEditView` хранит текст и параметры форматирования текста. `CRichEditDoc` ведет список OLE клиентские элементы, которые находятся в представлении. `CRichEditCntrItem` предоставляет доступ со стороны контейнера к элемент клиента OLE.

Это Windows общего элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанными классами) доступны только для программ, работающих в версиях Windows 95/98 и Windows NT 3.51 и более поздних версиях.

Пример использования представления rich edit в приложении MFC, см. в разделе [WORDPAD](../../visual-cpp-samples.md) пример приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>Требования

**Заголовок:** afxrich.h

##  <a name="adjustdialogposition"></a>  CRichEditView::AdjustDialogPosition

Вызывайте эту функцию, чтобы переместить указанном диалоговом окне, чтобы не скрывать текущего выделения.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>Параметры

*pDlg*<br/>
Указатель на `CDialog` объект.

##  <a name="canpaste"></a>  CRichEditView::CanPaste

Вызывайте эту функцию, чтобы определить, если буфер обмена содержит сведения, которые можно вставить в этом представлении rich edit.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если буфер обмена содержит данные в формате, который может принимать этого представления rich edit; в противном случае — 0.

##  <a name="cricheditview"></a>  CRichEditView::CRichEditView

Вызывайте эту функцию для создания `CRichEditView` объекта.

```
CRichEditView();
```

##  <a name="dopaste"></a>  CRichEditView::DoPaste

Эта функция вызывается для вставки элемента OLE в *dataobj* в данную коллекцию "rich edit" документ представление.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>Параметры

*dataobj*<br/>
[COleDataObject](../../mfc/reference/coledataobject-class.md) содержащий данные для вставки.

*CF*<br/>
Требуемый формат буфера обмена.

*hMetaPict*<br/>
Метафайл, представляющий элемент для вставки.

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию как часть реализации по умолчанию [QueryAcceptData](#queryacceptdata).

Эта функция определяет тип на основе результатов обработчика для Специальная вставка. Если *cf* равно 0, новый элемент используется текущий символическое представление. Если *cf* имеет ненулевое значение и *hMetaPict* не равно NULL, новый элемент использует *hMetaPict* для его представления.

##  <a name="findtext"></a>  CRichEditView::FindText

Вызывайте эту функцию для поиска указанного текста и установке его текущее выделение.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Содержит строку для поиска.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра.

*bWord*<br/>
Указывает, если при поиске следует учитывать только слово целиком, не части слов.

*bNext*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска — в конец буфера. Если значение равно FALSE, направление поиска — к началу буфера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение *lpszFind* текст найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция отображает курсор ожидания во время операции поиска.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple

Вызывайте эту функцию для поиска указанного текста и установке его текущее выделение.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Содержит строку для поиска.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра.

*bWord*<br/>
Указывает, если при поиске следует учитывать только слово целиком, не части слов.

*bNext*<br/>
Указывает направление поиска. Если значение равно TRUE, направление поиска — в конец буфера. Если значение равно FALSE, направление поиска — к началу буфера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение *lpszFind* текст найден; в противном случае 0.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::FindText](#findtext).

##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection

Вызывайте эту функцию для получения символа форматирование атрибуты текущего выделенного фрагмента.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) структуру, которая содержит символ форматирования атрибуты текущего выделенного фрагмента.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_GETCHARFORMAT](/windows/desktop/Controls/em-getcharformat) сообщение и [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) структуры в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData

Платформа вызывает эту функцию как часть обработки [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata).

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>Параметры

*lpchrg*<br/>
Указатель на [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) структуры, указывающий диапазон символов (и элементы OLE), чтобы скопировать в объект данных, определяемое *lplpdataobj*.

*dwReco*<br/>
Флаг операции буфера обмена. Может принимать одно из следующих значений.

- RECO_COPY Копировать в буфер обмена.

- RECO_CUT Вырезать в буфер обмена.

- Перетащите RECO_DRAG операции (операции перетаскивания).

- RECO_DROP Drop операции (операции перетаскивания).

- RECO_PASTE вставить из буфера обмена.

*lpRichDataObj*<br/>
Указатель на [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) объект, содержащий данные из буфера обмена из широкий набор функций элемента управления edit ( [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata)).

*lplpdataobj*<br/>
Указатель на указатель на переменную, которая получает адрес `IDataObject` объект, представляющий диапазон, указанный в *lpchrg* параметра. Значение *lplpdataobj* учитывается, если возвращается ошибка.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, сообщение об успехе операции. Дополнительные сведения о HRESULT см. в разделе [структуры из кодов ошибок модели COM](/windows/desktop/com/structure-of-com-error-codes) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Если возвращаемое значение указывает на успешное завершение, `IRichEditOleCallback::GetClipboardData` возвращает `IDataObject` осуществляется *lplpdataobj*; в противном случае он возвращает из них, доступ к *lpRichDataObj*. Переопределите эту функцию, чтобы указать собственные данные буфера обмена. Реализация по умолчанию эта функция возвращает E_NOTIMPL.

Существует расширенная переопределяемый.

Дополнительные сведения см. в разделе [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata), [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata), и [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) в Windows SDK и см. в разделе [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) в Windows SDK.

##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu

Платформа вызывает эту функцию как часть обработки [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu).

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>Параметры

*seltyp*<br/>
Тип выделения. Выбор типа значения описаны в разделе "Примечания".

*lpoleobj*<br/>
Указатель на `OLEOBJECT` структуры, указывающий первый выбранный объект OLE, если выделение содержит один или несколько элементов OLE. Если выделение не содержит элементов, *lpoleobj* имеет значение NULL. `OLEOBJECT` Структура содержит указатель на объект OLE v таблицу.

*lpchrg*<br/>
Указатель на [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) структуру, содержащую текущее выделение.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор в контекстном меню.

### <a name="remarks"></a>Примечания

Эта функция является обычной частью правой кнопки мыши вниз обработки.

Тип выделения может быть любое сочетание следующих флагов:

- SEL_EMPTY указывает на текущее выделение отсутствует.

- SEL_TEXT указывает, что текущее выделение содержит текст.

- SEL_OBJECT указывает, что текущее выделение содержит хотя бы один элемент OLE.

- SEL_MULTICHAR указывает, что текущее выделение содержит более одного символа текста.

- SEL_MULTIOBJECT указывает, что текущее выделение содержит более одного объекта OLE.

Реализация по умолчанию возвращает значение NULL. Существует расширенная переопределяемый.

Дополнительные сведения см. в разделе [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu) и [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) в пакете Windows SDK.

Дополнительные сведения о `OLEOBJECT` введите, см. в статье структур OLE данных и структура распределения *OLE знаний*.

##  <a name="getdocument"></a>  CRichEditView::GetDocument

Вызывайте эту функцию для получения указателя на `CRichEditDoc` связанный с этим представлением.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) объект, связанный с вашей `CRichEditView` объекта.

##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem

Вызов, эту функцию для получения OLE элемент, который в данный момент активации на месте в этом `CRichEditView` объекта.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель в одном месте, в активную [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта в этом представлении rich edit; Значение NULL, если нет элемента OLE в настоящее время в активном состоянии на месте.

##  <a name="getmargins"></a>  CRichEditView::GetMargins

Вызывайте эту функцию для получения текущего поля, используемые в печати.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Возвращаемое значение

Поля, используемые в печати, измеряемый в MM_TWIPS.

##  <a name="getpagerect"></a>  CRichEditView::GetPageRect

Вызывайте эту функцию, чтобы получить размеры страницы, используемые в печати.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Границы страницы, используемые в печати, измеряемый в MM_TWIPS.

### <a name="remarks"></a>Примечания

Это значение зависит от размера бумаги.

##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize

Вызывайте эту функцию, чтобы получить текущий размер бумаги.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер бумаги, используемые в печати, измеряемый в MM_TWIPS.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection

Вызывайте эту функцию, чтобы получить атрибуты текущего выделенного фрагмента форматирования абзаца.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) структуры, который содержит атрибуты текущего выделенного фрагмента форматирования абзаца.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [EM_GETPARAFORMAT](/windows/desktop/Controls/em-getparaformat) сообщение и [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) структуры в пакете Windows SDK.

##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect

Вызывайте эту функцию для получения границы области печати в прямоугольнике страницы.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Границы области изображения, используемые в печати, измеряемый в MM_TWIPS.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth

Вызывайте эту функцию, чтобы определить ширину области печати.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина области печати измеряется в MM_TWIPS.

##  <a name="getricheditctrl"></a>  CRichEditView::GetRichEditCtrl

Вызывайте эту функцию для получения [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) объект, связанный с `CRichEditView` объекта.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

`CRichEditCtrl` Объекта для этого представления.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::FindText](#findtext).

##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem

Вызывайте эту функцию для получения объекта OLE ( `CRichEditCntrItem` объекта) в данный момент выбран в этом `CRichEditView` объекта.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта, выбранного в `CRichEditView` объекта; Значение NULL, если элемент не выбран в этом представлении.

##  <a name="gettextlength"></a>  CRichEditView::GetTextLength

Вызывайте эту функцию для получения длины текста в данном `CRichEditView` объекта.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина текста в данном `CRichEditView` объекта.

##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx

Вызовите эту функцию-член для вычисления длины текста в данном `CRichEditView` объекта.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Значение, указывающее метод, используемый для определения длины текста. Этот член может иметь одно или несколько значений, перечисленных в элемент флаги [GETTEXTLENGTHEX](/windows/desktop/api/richedit/ns-richedit-_gettextlengthex) описано в пакете Windows SDK.

*uCodePage*<br/>
Кодовая страница для перевода (CP_ACP для кодовой страницы ANSI, 1200 для Юникода).

### <a name="return-value"></a>Возвращаемое значение

Число символов или байтов в элементе управления. Если были заданы несовместимые флаги в *dwFlags*, эта функция-член возвращает значение E_INVALIDARG.

### <a name="remarks"></a>Примечания

`GetTextLengthEx` предоставляет дополнительные способы определения длину текста. Он поддерживает функциональные возможности Rich Edit 2.0. Дополнительные сведения см. в разделе [о элементами управления Rich Edit](/windows/desktop/Controls/about-rich-edit-controls) в пакете Windows SDK.

##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject

Вызывайте эту функцию для вставки в указанный файл (как [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта) в расширенных изменить представление.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, содержащая имя файла для вставки.

##  <a name="insertitem"></a>  CRichEditView::InsertItem

Вызывайте эту функцию для вставки [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта в представлении rich edit.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент для вставки.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, указывающее на успешное вставки.

### <a name="remarks"></a>Примечания

Дополнительные сведения о HRESULT см. в разделе [структуры из кодов ошибок модели COM](/windows/desktop/com/structure-of-com-error-codes) в пакете Windows SDK.

##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat

Вызывайте эту функцию, чтобы определить, если *cf* — это формат буфера обмена, текста, форматированного текста или форматированного текста с помощью элементов OLE.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Формат буфера обмена интерес.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение *cf* имеет широкие возможности редактирования или текстовом формате буфера обмена.

##  <a name="isselected"></a>  CRichEditView::IsSelected

Вызывайте эту функцию, чтобы определить, если указанного элемента OLE в данный момент выбран в этом представлении.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Параметры

*pDocItem*<br/>
Указатель на объект в представлении.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект выделен; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если другой метод для обработки элементы OLE класс производным представлением.

##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent

Отступ для элементов маркированного списка в список. по умолчанию 720 единиц, который является 1/2 дюйма.

```
int m_nBulletIndent;
```

##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap

Указывает тип переноса слов для этого представления rich edit.

```
int m_nWordWrap;
```

### <a name="remarks"></a>Примечания

Одно из следующих значений:

- `WrapNone` Указывает не автоматический перенос.

- `WrapToWindow` Указывает, перенос слов на основе ширины окна.

- `WrapToTargetDevice` Указывает, перенос слов, с учетом характеристик целевого устройства.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::WrapChanged](#wrapchanged).

##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect

Вызывайте эту функцию, чтобы переключить форматирование эффекты для текущего выделения символов.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Параметры

*dwMask*<br/>
Символ форматирования эффекты для изменения в текущем выделении.

*dwEffect*<br/>
Список нужных форматирование эффекты для переключения символов.

### <a name="remarks"></a>Примечания

Каждый вызов этой функции переключает указанный эффекты форматирования для текущего выделения.

Дополнительные сведения о *dwMask* и *dwEffect* параметры и их возможные значения см. в разделе соответствующие члены данных [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

##  <a name="onfindnext"></a>  CRichEditView::OnFindNext

Вызывается платформой при обработке команды из диалогового окна поиска и замены.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Строка, которую надо найти.

*bNext*<br/>
Направление поиска: значение TRUE указывает вниз; Значение равно FALSE, вверх.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра.

*bWord*<br/>
Указывает, является ли поиск соответствия словам целиком только или нет.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для поиска текста внутри `CRichEditView`. Переопределите эту функцию для изменения характеристик поиска для класса производным представлением.

##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate

Вызвано структурой после представления впервые присоединяется к документу, но до изначально отображается представление.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция вызывает [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) функции-члена без указания сведений (то есть, используя значения по умолчанию 0 для *lHint* параметр и значение NULL для *pHint* параметр). Переопределите эту функцию, чтобы выполнить однократную инициализацию, которая требует сведений о документе. Например если приложение имеет документов фиксированного размера, можно использовать эту функцию для инициализации представления прокрутки ограничения в зависимости от размера документа. Если приложение поддерживает документы переменного размера, используйте `OnUpdate` обновить событие прокрутки, ограничивает при каждом изменении документов.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::m_nWordWrap](#m_nwordwrap).

##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject

Эту функцию можно используйте для загрузки данных в собственном формате из внедренного элемента.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>Параметры

*lpStg*<br/>
Указатель на [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) объекта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае — 0;

### <a name="remarks"></a>Примечания

Как правило, это делается путем создания [COleStreamFile](../../mfc/reference/colestreamfile-class.md) вокруг `IStorage`. `COleStreamFile` Можно подключить в архив и [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) вызывается для загрузки данных.

Существует расширенная переопределяемый.

Дополнительные сведения см. в разделе [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) в пакете Windows SDK.

##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign

Вызывайте эту функцию для изменения выравнивания абзаца для выделенных абзацев.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>Параметры

*wAlign*<br/>
Требуемое выравнивание абзаца. Одно из следующих значений:

- PFA_LEFT выравнивание абзацев в левом поле.

- PFA_RIGHT выровнять абзацы с правого поля.

- PFA_CENTER Center абзацев, находящаяся внутри полей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged

Переопределите эту функцию, чтобы изменить характеристики для этого представления rich edit, при изменении принтера.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>Параметры

*dcPrinter*<br/>
Объект [CDC](../../mfc/reference/cdc-class.md) объекта для нового принтера.

### <a name="remarks"></a>Примечания

Реализация по умолчанию задает размер бумаги для физических высоту и ширину для устройства вывода (принтера). Если есть контекст устройства, не связанная с *dcPrinter*, реализация по умолчанию задает размер бумаги для 8,5 х 11 дюймов.

##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll

Вызывается платформой при обработке команды "Заменить все" в диалоговом окне Replace.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Заменяемый текст.

*lpszReplace*<br/>
Текст замены.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра.

*bWord*<br/>
Указывает, если поиск необходимо выбрать слова целиком или нет.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы заменить все вхождения заданного текст другой строкой. Переопределите эту функцию, чтобы изменить характеристики поиска для данного представления.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::FindText](#findtext).

##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel

Вызывается платформой при обработке команды Replace из диалогового окна «Заменить».

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Заменяемый текст.

*bNext*<br/>
Указывает направление поиска: значение TRUE не работает; Значение равно FALSE, вверх.

*bCase*<br/>
Указывает, является ли поиск с учетом регистра.

*bWord*<br/>
Указывает, если поиск необходимо выбрать слова целиком или нет.

*lpszReplace*<br/>
Текст замены.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы заменить одно вхождение заданного текст другой строкой. Переопределите эту функцию, чтобы изменить характеристики поиска для данного представления.

##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound

Вызывается платформой, каждый раз, когда поиск заканчивается неудачно.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Текст, который не был найден.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы изменить выходные данные уведомления [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep).

Дополнительные сведения см. в разделе [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect

Платформа вызывает эту функцию, чтобы обновить командный пользовательский Интерфейс для команд эффект символ.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта.

*dwMask*<br/>
Указывает маску форматирование символов.

*dwEffect*<br/>
Указывает эффект форматирование символов.

### <a name="remarks"></a>Примечания

Маска *dwMask* указывает, какой знак атрибуты форматирования для проверки. Флаги *dwEffect* список атрибутов для набора или Очистить форматирование символов.

Дополнительные сведения о *dwMask* и *dwEffect* параметры и их возможные значения см. в разделе соответствующие члены данных [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign

Платформа вызывает эту функцию, чтобы обновить командный пользовательский Интерфейс для команд эффект абзаца.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта.

*wAlign*<br/>
Выравнивание абзаца для проверки. Одно из следующих значений:

- PFA_LEFT выравнивание абзацев в левом поле.

- PFA_RIGHT выровнять абзацы с правого поля.

- PFA_CENTER Center абзацев, находящаяся внутри полей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect

Вызывайте эту функцию для форматирования диапазон текста в элементе управления "rich edit" в соответствии с размерами *rectLayout* для устройства, определяемое *pDC*.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
Указатель на контекст устройства для области вывода.

*rectLayout*<br/>
[RECT](../../mfc/reference/rect-structure1.md) или [CRect](../../atl-mfc-shared/reference/crect-class.md) который определяет область вывода.

*nIndexStart*<br/>
Отсчитываемый от нуля индекс первого символа для форматирования.

*nIndexStop*<br/>
Отсчитываемый от нуля индекс последнего символа для форматирования.

*bOutput*<br/>
Указывает, следует ли отрисовывать текст. Если значение равно FALSE, текст только что измеряется.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа, который помещается в область вывода, плюс один.

### <a name="remarks"></a>Примечания

Как правило, этот вызов сопровождается вызов [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) служащего для выходных данных.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::GetPaperSize](#getpapersize).

##  <a name="printpage"></a>  CRichEditView::PrintPage

Вызывайте эту функцию для форматирования диапазон текста в элементе управления "rich edit" для выходных данных устройства, определяемое *pDC*.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
Указатель на контекст устройства для вывода страниц.

*nIndexStart*<br/>
Отсчитываемый от нуля индекс первого символа для форматирования.

*nIndexStop*<br/>
Отсчитываемый от нуля индекс последнего символа для форматирования.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего знака, которое может уместиться на странице плюс один.

### <a name="remarks"></a>Примечания

Управляет макетом каждой страницы [GetPageRect](#getpagerect) и [GetPrintRect](#getprintrect). Как правило, этот вызов сопровождается вызов [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) служащего для выходных данных.

Обратите внимание, что поля относятся к физической страницы, а не логической страницы. Таким образом поля нулевой часто обрезать текст, так как многие принтеры имеют непечатаемые области страницы. Во избежание обрезки текста, необходимо вызвать [SetMargins](#setmargins) и установка разумным полей перед печатью.

##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData

Вызывается платформой для вставки объекта в форматированным редактированием.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>Параметры

*lpdataobj*<br/>
Указатель на [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) для запроса.

*lpcfFormat*<br/>
Указатель на формат допустимые данные.

*dwReco*<br/>
Не используется.

*bReally*<br/>
Указывает, если операция вставки следует продолжить или нет.

*hMetaFile*<br/>
Дескриптор метафайла, используемый для рисования значка элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, сообщение об успехе операции.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для обработки различных организации COM элементов в документ в производном классе. Существует расширенная переопределяемый.

Дополнительные сведения о HRESULT и `IDataObject`, см. в разделе [структуры из кодов ошибок модели COM](/windows/desktop/com/structure-of-com-error-codes) и [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject), соответственно, в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat

Вызывайте эту функцию, чтобы задать атрибуты для нового текста в этом форматирование символов `CRichEditView` объекта.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
[CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) структуру, содержащую новый символ по умолчанию атрибуты форматирования.

### <a name="remarks"></a>Примечания

Только атрибуты, указанные фильтром `dwMask` членом *cf* изменяются при помощи этой функции.

Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](/windows/desktop/Controls/em-setcharformat) сообщение и [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) структуры в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="setmargins"></a>  CRichEditView::SetMargins

Вызывайте эту функцию для задайте границы печати для этого представления rich edit.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>Параметры

*rectMargin*<br/>
Новые значения полей для печати, измеряемый в MM_TWIPS.

### <a name="remarks"></a>Примечания

Если [m_nWordWrap](#m_nwordwrap) — `WrapToTargetDevice`, следует вызывать [WrapChanged](#wrapchanged) после использования этой функции для настройки печати характеристики.

Обратите внимание, что используемые поля [PrintPage](#printpage) относительны физической страницы, а не логической страницы. Таким образом поля нулевой часто обрезать текст, так как многие принтеры имеют непечатаемые области страницы. Во избежание обрезки текста, следует вызывать используйте `SetMargins` Установка полей разумным принтера перед печатью.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::GetPaperSize](#getpapersize).

##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize

Вызовите эту функцию для задания размера бумаги для печати этого представления rich edit.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>Параметры

*sizePaper*<br/>
Новые значения размера бумаги для печати, измеряемый в MM_TWIPS.

### <a name="remarks"></a>Примечания

Если [m_nWordWrap](#m_nwordwrap) — `WrapToTargetDevice`, следует вызывать [WrapChanged](#wrapchanged) после использования этой функции для настройки печати характеристики.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat

Вызывайте эту функцию, чтобы задать атрибуты для текущего выделения в этом форматирования абзаца `CRichEditView` объекта.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>Параметры

*Общая папка*<br/>
[PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) атрибуты форматирования абзаца структура, содержащая новое значение по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Только атрибуты, указанные фильтром `dwMask` членом *pf* изменяются при помощи этой функции.

Дополнительные сведения см. в разделе [EM_SETPARAFORMAT](/windows/desktop/Controls/em-setparaformat) сообщение и [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) структуры в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

##  <a name="textnotfound"></a>  CRichEditView::TextNotFound

Вызывайте эту функцию для сброса состояния внутреннего поиска [CRichEditView](../../mfc/reference/cricheditview-class.md) управления после ошибки вызова [FindText](#findtext).

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Параметры

*lpszFind*<br/>
Содержит текстовую строку, не найден.

### <a name="remarks"></a>Примечания

Рекомендуется, что этот метод вызываться сразу после неудачных вызовов для [FindText](#findtext) таким образом, чтобы правильно сбрасывается состояние внутреннего поиска элемента управления.

*LpszFind* параметр должен содержать то же содержимое, что строка, предоставляемая [FindText](#findtext). После сброса состояния внутреннего поиска, этот метод будет вызывать [OnTextNotFound](#ontextnotfound) метод с предоставленным искомой строки.

### <a name="example"></a>Пример

  См. в примере [CRichEditView::FindText](#findtext).

##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged

Эта функция вызывается при изменении характеристики печати ( [SetMargins](#setmargins) или [SetPaperSize](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>Примечания

Эту функцию, чтобы изменить способ представления с форматированием реагирует на изменения в переопределение [m_nWordWrap](#m_nwordwrap) или характеристики печати ( [OnPrinterChanged](#onprinterchanged)).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC WORDPAD](../../visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)
