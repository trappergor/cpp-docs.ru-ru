---
title: CRichEditView-класс | Документы Microsoft
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
ms.openlocfilehash: 353a45cad513e9c862b6ae6c15ab5383d3d65d48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cricheditview-class"></a>CRichEditView-класс
С [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), предоставляет функциональные возможности элемента управления форматированным редактированием в контексте архитектуры представлений документов MFC.  
  
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
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Свернуть диалоговое окно не мешает читать текущее выделение.|  
|[CRichEditView::CanPaste](#canpaste)|Указывает, содержит ли буфер данных, которые могут быть вставлены в представлении rich edit.|  
|[CRichEditView::DoPaste](#dopaste)|Вставка элемента OLE в этом представлении rich edit.|  
|[CRichEditView::FindText](#findtext)|Выполняет поиск указанного текста, курсор ожидания вызова.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|Выполняет поиск указанного текста.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Извлекает атрибуты для текущего выделения форматирование символов.|  
|[CRichEditView::GetDocument](#getdocument)|Извлекает указатель на связанный [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Получает элемент OLE, активная в настоящее время на месте в представлении rich edit.|  
|[CRichEditView::GetMargins](#getmargins)|Возвращает значение поля для этого представления rich edit.|  
|[CRichEditView::GetPageRect](#getpagerect)|Возвращает прямоугольник, страница для этого представления rich edit.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Получает размер бумаги для этого представления rich edit.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Извлекает атрибуты для текущего выделения форматирования абзаца.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Возвращает прямоугольник, печати для этого представления rich edit.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Получает ширину печати для этого представления rich edit.|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Извлекает элемент управления форматированием.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|Получает элемент, выбранный из представления rich edit.|  
|[CRichEditView::GetTextLength](#gettextlength)|Получает длину текста в представлении rich edit.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Возвращает число символов или байтов, в представлении rich edit. Список развернутой флаг для способом определения размера.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Вставляет файл как объект OLE.|  
|[CRichEditView::InsertItem](#insertitem)|Вставляет элемент в виде объекта OLE.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Указывает, содержит ли буфер данных форматируемого или формат текста.|  
|[CRichEditView::OnCharEffect](#onchareffect)|Переключает форматирование для выделенного символов.|  
|[CRichEditView::OnParaAlign](#onparaalign)|Изменение выравнивания абзаца.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Обновляет пользовательский Интерфейс команды для символа открытые функции-члены.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Обновляет пользовательский Интерфейс команды для абзаца открытые функции-члены.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|Форматирует указанный текст в пределах заданного прямоугольника.|  
|[CRichEditView::PrintPage](#printpage)|Форматирует указанный текст на данной странице.|  
|[CRichEditView::SetCharFormat](#setcharformat)|Задает атрибуты для текущего выделения форматирование символов.|  
|[CRichEditView::SetMargins](#setmargins)|Задает поля для этого rich изменить представление.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Задает размер бумаги для этого представления rich edit.|  
|[CRichEditView::SetParaFormat](#setparaformat)|Задает атрибуты для текущего выделения форматирования абзаца.|  
|[CRichEditView::TextNotFound](#textnotfound)|Сбрасывает состояние внутреннего поиска элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|Получает объект Clipboard для диапазона в этом представлении rich edit.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|Получает контекстное меню для использования в правой-нажатия кнопки мыши.|  
|[CRichEditView::IsSelected](#isselected)|Указывает, если данный элемент OLE выбрана или нет.|  
|[CRichEditView::OnFindNext](#onfindnext)|Поиск следующего вхождения подстроки.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Обновляет представление, при первом связана с документом.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Получает машинные данные из объекта OLE.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Устанавливает параметры печати для заданного устройства.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|Заменяет все вхождения заданной строки новую строку.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|Заменяет текущее выделение.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Обрабатывает уведомление пользователя, запрошенный текст не найден.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Запросы для просмотра о данных на `IDataObject`.|  
|[CRichEditView::WrapChanged](#wrapchanged)|Настраивает целевое устройство вывода для этого представления, основанного на значение форматированием `m_nWordWrap`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Указывает отступ для маркеров списков.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Указывает ограничения переноса слов.|  
  
## <a name="remarks"></a>Примечания  
 Управления rich edit «» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может содержать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView` Сохраняет текст и параметры форматирования текста. `CRichEditDoc` поддерживает список клиентских элементов управления OLE, находящихся в представлении. `CRichEditCntrItem` Предоставляет контейнер стороне доступ к элемент клиента OLE.  
  
 Это Windows стандартного элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанные классы) доступен только для программ, под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних.  
  
 Пример использования представления rich edit в приложениях MFC см. в разделе [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
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
 Эта функция вызывается для перемещения указанном диалоговом окне, чтобы не скрывать текущее выделение.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>Параметры  
 *pDlg*  
 Указатель на `CDialog` объект.  
  
##  <a name="canpaste"></a>  CRichEditView::CanPaste  
 Эта функция вызывается для определения, содержит ли буфер обмена сведения, которые могут быть вставлены в этом представлении rich edit.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в буфере обмена содержатся данные в формате, который может принимать этого представления rich edit; в противном случае — 0.  
  
##  <a name="cricheditview"></a>  CRichEditView::CRichEditView  
 Эта функция вызывается для создания `CRichEditView` объекта.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>  CRichEditView::DoPaste  
 Эта функция вызывается для вставки элемента OLE в `dataobj` в этот "rich edit" документ представление.  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>Параметры  
 `dataobj`  
 [COleDataObject](../../mfc/reference/coledataobject-class.md) содержащий данные для вставки.  
  
 `cf`  
 Требуемый формат буфера обмена.  
  
 `hMetaPict`  
 Метафайл, представляющий вставляемый элемент.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию как часть реализации по умолчанию [QueryAcceptData](#queryacceptdata).  
  
 Эта функция определяет тип на основе результатов обработчика для Специальная вставка. Если `cf` равно 0, то новый элемент использует текущее представление преобразованного в значок. Если `cf` отлично от нуля и `hMetaPict` не **NULL**, использует новый элемент `hMetaPict` для его представления.  
  
##  <a name="findtext"></a>  CRichEditView::FindText  
 Эта функция используется для поиска указанного текста и сделать его текущее выделение.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Содержит строку для поиска.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, если при поиске следует учитывать только целые слова, не частей слова.  
  
 `bNext`  
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска находится ближе к началу буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `lpszFind` текст найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция отображает курсор ожидания во время операции поиска.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple  
 Эта функция используется для поиска указанного текста и сделать его текущее выделение.  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Содержит строку для поиска.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, если при поиске следует учитывать только целые слова, не частей слова.  
  
 `bNext`  
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска находится ближе к началу буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `lpszFind` текст найден; в противном случае — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::FindText](#findtext).  
  
##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection  
 Эта функция вызывается для получения символа форматирование атрибуты текущего выделенного фрагмента.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, которая содержит символ форматирования атрибуты текущего выделенного фрагмента.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) сообщений и [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуры в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData  
 Платформа вызывает эту функцию как часть обработки [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315).  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>Параметры  
 `lpchrg`  
 Указатель на [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структуры указания диапазона символов (и OLE-элементы) для копирования данных объекта, заданного параметром `lplpdataobj`.  
  
 `dwReco`  
 Флаг операции в буфер обмена. Может принимать одно из следующих значений.  
  
- **RECO_COPY** скопировать в буфер обмена.  
  
- **RECO_CUT** Вырезать в буфер обмена.  
  
- **RECO_DRAG** перетащите операции (операции перетаскивания).  
  
- **RECO_DROP** Drop операции (операции перетаскивания).  
  
- **RECO_PASTE** вставить из буфера обмена.  
  
 `lpRichDataObj`  
 Указатель на [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) объект, содержащий данные из буфера обмена с использованием разнообразных элемента управления edit ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 Указатель на переменную указатель, получающий адрес `IDataObject` объект, представляющий диапазон, указанный в `lpchrg` параметра. Значение `lplpdataobj` учитывается, если возвращается сообщение об ошибке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение reporting успешное выполнение. Дополнительные сведения о `HRESULT`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение указывает на успешное завершение, **IRichEditOleCallback::GetClipboardData** возвращает `IDataObject` обращаются `lplpdataobj`; в противном случае он возвращает контейнер, доступ к `lpRichDataObj`. Переопределите эту функцию для предоставления данных буфера обмена. Реализация по умолчанию эта функция возвращает **E_NOTIMPL**.  
  
 Существует расширенная overridable.  
  
 Дополнительные сведения см. в разделе [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), и [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) в Windows SDK и разделе [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) в Windows SDK.  
  
##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu  
 Платформа вызывает эту функцию как часть обработки [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317).  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>Параметры  
 *seltyp*  
 Тип выбора. Выбор типа значения описаны в разделе "Примечания".  
  
 `lpoleobj`  
 Указатель на **OLEOBJECT** структура, задающая первого выбранного объекта OLE, если выбор содержит один или несколько элементов OLE. Если выделение не содержит элементов, `lpoleobj` — **NULL**. **OLEOBJECT** структура содержит указатель на объект OLE v таблицу.  
  
 `lpchrg`  
 Указатель на [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структуру, содержащую текущее выделение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор в контекстном меню.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно входит правой кнопки мыши времени обработки.  
  
 Выбор типа может быть любое сочетание следующих флагов:  
  
- `SEL_EMPTY` Указывает, что отсутствует текущий выбранный текст.  
  
- `SEL_TEXT` Указывает, что текущее выделение содержит текст.  
  
- `SEL_OBJECT` Указывает, что текущий выделенный фрагмент содержит хотя бы один элемент OLE.  
  
- `SEL_MULTICHAR` Указывает, что текущее выделение содержит более одного символа в тексте.  
  
- `SEL_MULTIOBJECT` Указывает, что текущее выделение содержит более одного объекта OLE.  
  
 Реализация по умолчанию возвращает **NULL**. Существует расширенная overridable.  
  
 Дополнительные сведения см. в разделе [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) и [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) в Windows SDK.  
  
 Дополнительные сведения о **OLEOBJECT** введите, см. в статье OLE структуры и данных структуры распределения в *OLE Knowledge Base*.  
  
##  <a name="getdocument"></a>  CRichEditView::GetDocument  
 Эта функция вызывается для получения указателя на `CRichEditDoc` связанный с этим представлением.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) объект, связанный с вашей `CRichEditView` объекта.  
  
##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem  
 Вызов эту функцию для получения OLE элементом, к которому в данный момент активации на месте в этом `CRichEditView` объекта.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на одном месте, в активной [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта в этом представлении rich edit; **NULL** Если нет элемента OLE в данный момент в активном состоянии на месте.  
  
##  <a name="getmargins"></a>  CRichEditView::GetMargins  
 Эта функция вызывается для получения текущего поля, используемые при печати.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поля, используемые при печати, измеряется в `MM_TWIPS`.  
  
##  <a name="getpagerect"></a>  CRichEditView::GetPageRect  
 Эта функция вызывается для получения размеров страницы, используемой при печати.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Границы страница, используемая для печати, измеряется в `MM_TWIPS`.  
  
### <a name="remarks"></a>Примечания  
 Это значение зависит от размера бумаги.  
  
##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize  
 Эта функция вызывается для получения текущего размера бумаги.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер бумаги, используемой при печати, измеряется в `MM_TWIPS`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection  
 Вызовите эту функцию для получения атрибуты текущего выделенного фрагмента форматирования абзаца.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) структуру, содержащую атрибуты текущего выделенного фрагмента форматирования абзаца.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) сообщений и [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) структуры в Windows SDK.  
  
##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect  
 Эта функция вызывается для получения границы области печати страницы прямоугольника.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Границы области изображения, используемые в печати, измеряется в `MM_TWIPS`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth  
 Эта функция вызывается для определения ширины области печати.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина области печати измеряется `MM_TWIPS`.  
  
##  <a name="getricheditctrl"></a>  CRichEditView::GetRichEditCtrl  
 Эта функция вызывается для получения [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) объекта, связанного с `CRichEditView` объекта.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CRichEditCtrl` Объекта для этого представления.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::FindText](#findtext).  
  
##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem  
 Эта функция вызывается для получения объекта OLE ( `CRichEditCntrItem` объектов) в данный момент выбран в этом `CRichEditView` объекта.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта, выбранного в `CRichEditView` объекта; **NULL** Если не выбран элемент в этом представлении.  
  
##  <a name="gettextlength"></a>  CRichEditView::GetTextLength  
 Эта функция вызывается для получения длины текста в данном `CRichEditView` объекта.  
  
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
 `dwFlags`  
 Значение, указывающее метод, который используется для определения длины текста. Этот элемент может иметь одно или несколько значений, приведенных в флаги членом [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) описано в Windows SDK.  
  
 `uCodePage`  
 Кодовая страница для перевода (CP_ACP для кодовой страницы ANSI, 1200 Юникода).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов или байтов, в поле редактирования. Если были установлены несовместимые флаги `dwFlags`, эта функция-член возвращает `E_INVALIDARG`.  
  
### <a name="remarks"></a>Примечания  
 `GetTextLengthEx` Существуют дополнительные способы определения длины текста. Он поддерживает функции Rich Edit 2.0. Дополнительные сведения см. в разделе [о элементами управления Rich Edit](http://msdn.microsoft.com/library/windows/desktop/bb787873) в Windows SDK.  
  
##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject  
 Эта функция вызывается для вставки в указанный файл (как [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объектов) в форматированного изменить представление.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, содержащая имя файла для вставки.  
  
##  <a name="insertitem"></a>  CRichEditView::InsertItem  
 Эта функция вызывается для вставки [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объект в представлении rich edit.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на элемент для вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение, указывающее на успешное вставки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о `HRESULT`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK.  
  
##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat  
 Эта функция вызывается для определения `cf` — это формат буфера обмена текста, форматированного текста или форматированного текста с OLE-элементы.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 Формат буфера обмена, представляющие интерес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `cf` имеет широкие возможности редактирования или текстовом формате буфера обмена.  
  
##  <a name="isselected"></a>  CRichEditView::IsSelected  
 Эта функция вызывается для определения выбранного в данный момент в этом представлении указанного элемента OLE.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pDocItem`  
 Указатель на объект в представлении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выбран объект; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если класс производным представлением различных методов обработки выбранных элементов OLE.  
  
##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent  
 Отступ для маркеров элементов в списке; по умолчанию 720 единиц составляет 1/2 дюйма.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap  
 Указывает тип для этого представления rich edit перенос по словам.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Примечания  
 Одно из следующих значений:  
  
- `WrapNone` Указывает не автоматический перенос.  
  
- `WrapToWindow` Указывает, перенос слов, исходя из ширины окна.  
  
- `WrapToTargetDevice` Указывает, перенос слов на основе характеристик целевого устройства.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::WrapChanged](#wrapchanged).  
  
##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect  
 Вызывайте эту функцию, чтобы включить или отключить форматирование эффекты для выбранных символов.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMask`  
 Символ форматирования эффекты для изменения в текущем выделенном фрагменте.  
  
 `dwEffect`  
 Требуемый список эффектов, чтобы включить или отключить форматирование знаков.  
  
### <a name="remarks"></a>Примечания  
 Каждый вызов этой функции переключает указанного эффекты форматирования для текущего выделения.  
  
 Дополнительные сведения о `dwMask` и `dwEffect` параметров и их возможных значений см. соответствующие члены данных [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) в Windows SDK.  
  
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
 `lpszFind`  
 Строка, которую надо найти.  
  
 `bNext`  
 Направление поиска: **TRUE** указывает вниз; **FALSE**, до.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, является ли поиск соответствия словам целиком только или нет.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию для поиска текста в `CRichEditView`. Переопределите эту функцию для изменения характеристик поиска для класса производным представлением.  
  
##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate  
 Вызывается платформой после представление впервые присоединяется к документу, но до первоначального отображения представления.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) функции-члена без указания информации (то есть, используя значения по умолчанию 0 для `lHint` параметр и **NULL** для `pHint` параметр). Переопределите эту функцию, чтобы выполнить однократную инициализацию, которая требуется сведения о документе. Например если приложение имеет документов фиксированного размера, можно использовать эту функцию для инициализации представления прокрутки ограничения в зависимости от размера документа. Если приложение поддерживает документы переменного размера, используйте `OnUpdate` обновление прокрутки ограничивает каждый раз изменения документа.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::m_nWordWrap](#m_nwordwrap).  
  
##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject  
 Эту функцию можно используйте для загрузки данных в собственном формате из встроенного элемента.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>Параметры  
 *lpStg*  
 Указатель на [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0;  
  
### <a name="remarks"></a>Примечания  
 Как правило, это делается путем создания [COleStreamFile](../../mfc/reference/colestreamfile-class.md) вокруг `IStorage`. `COleStreamFile` Могут прикрепляться в архив и [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) вызывается для загрузки данных.  
  
 Существует расширенная overridable.  
  
 Дополнительные сведения см. в разделе [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) в Windows SDK.  
  
##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign  
 Эта функция используется для изменения выравнивания абзаца для выделенных абзацев.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>Параметры  
 `wAlign`  
 Требуемое выравнивание абзаца. Одно из следующих значений:  
  
- `PFA_LEFT` Выравнивание абзацев по левой границе.  
  
- `PFA_RIGHT` Выравнивание абзацев с правого поля.  
  
- `PFA_CENTER` Выравнивание по центру абзацев между полями.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged  
 Переопределите эту функцию, чтобы изменить параметры для этого представления rich edit при изменении принтера.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>Параметры  
 `dcPrinter`  
 Объект [CDC](../../mfc/reference/cdc-class.md) объекта для нового принтера.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает размер бумаги для физического высоту и ширину устройство вывода (принтер). При наличии контекст устройства, не связанных с `dcPrinter`, реализация по умолчанию задает размер бумаги для 8,5 х 11 дюймов.  
  
##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll  
 Вызывается платформой при обработке заменить все команды из диалогового окна «Заменить».  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Заменяемый текст.  
  
 `lpszReplace`  
 Текст замены.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, если поиск необходимо выбрать слова целиком или нет.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для замены всех вхождений данного текст на другую строку. Переопределите эту функцию, чтобы изменить параметры поиска для данного представления.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::FindText](#findtext).  
  
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
 `lpszFind`  
 Заменяемый текст.  
  
 `bNext`  
 Указывает направление поиска: **TRUE** не работает; **FALSE**, до.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, если поиск необходимо выбрать слова целиком или нет.  
  
 `lpszReplace`  
 Текст замены.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию для замены одного вхождения заданного текст на другую строку. Переопределите эту функцию, чтобы изменить параметры поиска для данного представления.  
  
##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound  
 Вызывается платформой, если поиск заканчивается неудачей.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который не был найден.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для изменения вывода уведомления [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356).  
  
 Дополнительные сведения см. в разделе [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect  
 Платформа вызывает эту функцию для обновления команды пользовательского интерфейса для команд эффект символ.  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта.  
  
 `dwMask`  
 Указывает маску форматирование символов.  
  
 `dwEffect`  
 Указывает эффект форматирование символов.  
  
### <a name="remarks"></a>Примечания  
 Маска `dwMask` указывает, какой знак атрибуты форматирования для проверки. Флаги `dwEffect` список атрибутов, набор или снимите форматирование символов.  
  
 Дополнительные сведения о `dwMask` и `dwEffect` параметров и их возможных значений см. соответствующие члены данных [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign  
 Платформа вызывает эту функцию для обновления команды пользовательского интерфейса для команд эффект абзаца.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта.  
  
 `wAlign`  
 Выравнивание абзаца, для проверки. Одно из следующих значений:  
  
- `PFA_LEFT` Выравнивание абзацев по левой границе.  
  
- `PFA_RIGHT` Выравнивание абзацев с правого поля.  
  
- `PFA_CENTER` Выравнивание по центру абзацев между полями.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect  
 Эта функция вызывается для форматирования диапазон текста в элементе управления "rich edit" в соответствии с размерами *rectLayout* для устройства, заданные `pDC`.  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства для области вывода.  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md) или [CRect](../../atl-mfc-shared/reference/crect-class.md) определяющего области вывода.  
  
 `nIndexStart`  
 Отсчитываемый от нуля индекс первого символа для форматирования.  
  
 `nIndexStop`  
 Отсчитываемый от нуля индекс последнего символа для форматирования.  
  
 *bOutput*  
 Указывает, должно подготавливаться к просмотру текста. Если **FALSE**, текст только что измеряется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс последнего символа, который помещается в области вывода плюс один.  
  
### <a name="remarks"></a>Примечания  
 Как правило, этот вызов сопровождается вызов [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) которого создает выходные данные.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="printpage"></a>  CRichEditView::PrintPage  
 Эта функция вызывается для форматирования диапазон текста в элементе управления "rich edit" для вывода устройства, заданные `pDC`.  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства для вывода страниц.  
  
 `nIndexStart`  
 Отсчитываемый от нуля индекс первого символа для форматирования.  
  
 `nIndexStop`  
 Отсчитываемый от нуля индекс последнего символа для форматирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс последнего знака, которое может уместиться на странице плюс один.  
  
### <a name="remarks"></a>Примечания  
 Макет для каждой страницы управляется [GetPageRect](#getpagerect) и [GetPrintRect](#getprintrect). Как правило, этот вызов сопровождается вызов [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) которого создает выходные данные.  
  
 Обратите внимание, что поля относятся к физической, а не логической страницы. Таким образом поля нулевой часто обрезает текст, так как многие принтеры имеют непечатаемые области страницы. Во избежание обрезки текста, необходимо вызвать [SetMargins](#setmargins) и установка слишком много полей перед печатью.  
  
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
 *lpdataobj*  
 Указатель на [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) для запроса.  
  
 *lpcfFormat*  
 Указатель на формат допустимые данные.  
  
 `dwReco`  
 Не используется.  
  
 *bReally*  
 Указывает, если операция вставки должен быть продолжен или нет.  
  
 `hMetaFile`  
 Дескриптор метафайла, используемую для рисования значка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение reporting успешное выполнение.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обработки различных организации COM элементов в документ в производном классе. Существует расширенная overridable.  
  
 Дополнительные сведения о `HRESULT` и `IDataObject`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) и [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), соответственно, в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat  
 Вызывайте эту функцию, чтобы задать атрибуты для нового текста в данном форматирование символов `CRichEditView` объекта.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, содержащую новый атрибутов форматирования символов по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Атрибутами, заданными **dwMask** членом `cf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) сообщений и [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуры в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>  CRichEditView::SetMargins  
 Вызовите эту функцию для задания поля печати для этого представления rich edit.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>Параметры  
 *rectMargin*  
 Новые значения полей для печати, измеряется в `MM_TWIPS`.  
  
### <a name="remarks"></a>Примечания  
 Если [свойства m_nWordWrap](#m_nwordwrap) — `WrapToTargetDevice`, необходимо вызвать [WrapChanged](#wrapchanged) после использования этой функции для настройки печати характеристики.  
  
 Обратите внимание, что используемые поля [PrintPage](#printpage) относятся к физической, а не логической страницы. Таким образом поля нулевой часто обрезает текст, так как многие принтеры имеют непечатаемые области страницы. Во избежание обрезки текста, необходимо вызвать используйте `SetMargins` Установка принтера слишком много полей перед печатью.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize  
 Вызовите эту функцию для задания размера бумаги для печати этого представления rich edit.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>Параметры  
 *sizePaper*  
 Новые значения размера бумаги для печати, измеряется в `MM_TWIPS`.  
  
### <a name="remarks"></a>Примечания  
 Если [свойства m_nWordWrap](#m_nwordwrap) — `WrapToTargetDevice`, необходимо вызвать [WrapChanged](#wrapchanged) после использования этой функции для настройки печати характеристики.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat  
 Вызывайте эту функцию, чтобы задать атрибуты для текущего выделения в этом форматирования абзаца `CRichEditView` объекта.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Параметры  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) атрибуты форматирования абзаца структура, содержащая новое значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Атрибутами, заданными **dwMask** членом `pf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) сообщений и [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) структуры в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>  CRichEditView::TextNotFound  
 Эта функция вызывается для сброса состояния внутреннего поиска [CRichEditView](../../mfc/reference/cricheditview-class.md) управления после ошибки вызова [строки FindText](#findtext).  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Содержит текстовую строку, не найден.  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется, вызывать этот метод непосредственно после неудачных вызовов [строки FindText](#findtext) , чтобы правильно сбрасывается состояние внутреннего поиска элемента управления.  
  
 `lpszFind` Параметр должен включать одинаковое содержимое строка, предоставленная для [строки FindText](#findtext). После сброса состояния внутреннего поиска, этот метод будет вызывать [OnTextNotFound](#ontextnotfound) метод с предоставленным искомой строки.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CRichEditView::FindText](#findtext).  
  
##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged  
 Эта функция вызывается при изменении характеристики печати ( [SetMargins](#setmargins) или [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределение эту функцию, чтобы изменить способ rich edit представление реагирует на изменения в [свойства m_nWordWrap](#m_nwordwrap) или характеристики печати ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-класс](../../mfc/reference/cricheditdoc-class.md)   
 [Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)
