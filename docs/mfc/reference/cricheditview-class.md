---
title: "CRichEditView-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- document/view architecture, rich edit controls
- OLE containers, rich edit
- rich edit controls, OLE container
- CRichEditView class
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
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
ms.openlocfilehash: 9f54ec0c8aae58828607b01973a263e458c30ddb
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditview-class"></a>CRichEditView-класс
С [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) и [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), предоставляет функциональные возможности управления "rich edit" в контексте архитектуры представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|Создает объект `CRichEditView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|Свернуть диалоговое окно не мешает читать текущее выделение.|  
|[CRichEditView::CanPaste](#canpaste)|Указывает, содержит ли буфер данных, которые могут быть вставлены в представление широкими возможностями редактирования.|  
|[CRichEditView::DoPaste](#dopaste)|Вставляет в этом представлении форматируемого объекта OLE.|  
|[CRichEditView::FindText](#findtext)|Выполняет поиск указанного текста, курсор ожидания вызова.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|Выполняет поиск указанного текста.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|Возвращает символ форматирования атрибуты для текущего выделения.|  
|[CRichEditView::GetDocument](#getdocument)|Извлекает указатель на связанную [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|Извлекает элемент OLE, который является активным в данный момент на месте в представлении форматируемого.|  
|[CRichEditView::GetMargins](#getmargins)|Получает поля форматируемого представления.|  
|[CRichEditView::GetPageRect](#getpagerect)|Получает размер страницы для этого представления форматируемого.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Получает размер бумаги для этого представления форматируемого.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|Получает атрибуты для текущего выбора форматирования абзаца.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Возвращает прямоугольник, печати для этого представления форматируемого.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Получает ширину печати для этого представления форматируемого.|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Извлекает элемент управления форматированием.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|Получает элемент, выбранный в представлении форматируемого.|  
|[CRichEditView::GetTextLength](#gettextlength)|Получает длину в представлении форматируемого текста.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Возвращает число символов или байтов в представлении форматируемого. Список развернутой флаг для метода определения длины.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|Вставляет файл как элемент OLE.|  
|[CRichEditView::InsertItem](#insertitem)|Вставляет новый элемент в качестве объекта OLE.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|Указывает, содержит ли буфер данных форматируемого или текстовом формате.|  
|[CRichEditView::OnCharEffect](#onchareffect)|Переключает символ форматирования для текущего выделения.|  
|[CRichEditView::OnParaAlign](#onparaalign)|Изменение выравнивания абзаца.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|Обновляет пользовательский Интерфейс команд для символа открытыми функциями-членами.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|Обновляет пользовательский Интерфейс команд для абзаца открытые функции-члены.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|Форматирует указанный текст в данном прямоугольнике.|  
|[CRichEditView::PrintPage](#printpage)|Форматирует указанный текст на данной странице.|  
|[CRichEditView::SetCharFormat](#setcharformat)|Задает атрибуты для текущего выделения форматирование знаков.|  
|[CRichEditView::SetMargins](#setmargins)|Задает поля для этого широкие возможности изменить представление.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Задает размер бумаги для этого представления форматируемого.|  
|[CRichEditView::SetParaFormat](#setparaformat)|Задает атрибуты для текущего выбора форматирования абзаца.|  
|[CRichEditView::TextNotFound](#textnotfound)|Сбрасывает состояние внутреннего поиска элемента управления.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|Извлекает объект буфера обмена для диапазона в этом представлении форматируемого.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|Возвращает контекстное меню для использования в правой-нажатия кнопки мыши.|  
|[CRichEditView::IsSelected](#isselected)|Указывает, если заданный элемент OLE выбирается или нет.|  
|[CRichEditView::OnFindNext](#onfindnext)|Поиск следующего вхождения подстроки.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|Обновляет представление, при первом присоединенного к документу.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|Получает машинные данные из объекта OLE.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|Устанавливает параметры печати для заданного устройства.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|Заменяет все вхождения заданной строки с новой строки.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|Заменяет текущее выделение.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|Обрабатывает уведомление пользователя, запрошенный текст не найден.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|Запросы для просмотра о данных на `IDataObject`.|  
|[CRichEditView::WrapChanged](#wrapchanged)|Настройка целевого устройства вывода для этого широкие возможности изменять представление, основанное на значение `m_nWordWrap`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|Указывает отступ для маркеров списков.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|Указывает ограничения переноса слов.|  
  
## <a name="remarks"></a>Примечания  
 «Управления rich edit» — это окно, в котором пользователь может вводить и редактировать текст. Текст можно назначить форматирование знаков и абзацев и может включать внедренные объекты OLE. Элементы управления rich edit предоставляют программный интерфейс для форматирования текста. Тем не менее приложение должно реализовать все компоненты пользовательского интерфейса, необходимые для предоставления пользователю операций форматирования.  
  
 `CRichEditView`Сохраняет текст и параметры форматирования текста. `CRichEditDoc`поддерживает список клиентских элементов управления OLE, находящиеся в представлении. `CRichEditCntrItem`предоставляет доступ стороне контейнера для клиентского объекта OLE.  
  
 Это Windows стандартного элемента управления (и, следовательно, [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) и связанными классами) доступны только для программы под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних версий.  
  
 Пример использования форматируемого представления в приложении MFC, в разделе [WORDPAD](../../visual-cpp-samples.md) образец приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrich.h  
  
##  <a name="adjustdialogposition"></a>CRichEditView::AdjustDialogPosition  
 Эта функция вызывается для переместите заданного диалоговое окно, чтобы не скрывать текущее выделение.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>Параметры  
 *pDlg*  
 Указатель на `CDialog` объект.  
  
##  <a name="canpaste"></a>CRichEditView::CanPaste  
 Эта функция вызывается для определения, содержит ли буфер обмена сведения, которые могут быть вставлены в этом представлении форматируемого.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в буфере обмена содержатся данные в формате, который может принимать это представление форматируемого; в противном случае — 0.  
  
##  <a name="cricheditview"></a>CRichEditView::CRichEditView  
 Эта функция вызывается для создания `CRichEditView` объекта.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>CRichEditView::DoPaste  
 Эта функция вызывается для вставки объекта OLE в `dataobj` в эту "rich edit" документ представление.  
  
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
 Эта функция вызывается как часть реализации по умолчанию [QueryAcceptData](#queryacceptdata).  
  
 Эта функция определяет тип на основе результатов обработчика для Специальная вставка. Если `cf` равно 0, использует новый элемент текущего символическое представление. Если `cf` имеет ненулевое значение и `hMetaPict` не **NULL**, использует новый элемент `hMetaPict` для его представления.  
  
##  <a name="findtext"></a>CRichEditView::FindText  
 Эта функция используется для поиска указанного текста и устанавливаю ее в текущее выделение.  
  
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
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска — к началу буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `lpszFind` текст найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция отображает курсор ожидания во время операции поиска.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#151;](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>CRichEditView::FindTextSimple  
 Эта функция используется для поиска указанного текста и устанавливаю ее в текущее выделение.  
  
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
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска — к началу буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `lpszFind` текст найден; в противном случае — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::FindText](#findtext).  
  
##  <a name="getcharformatselection"></a>CRichEditView::GetCharFormatSelection  
 Эта функция вызывается для получения атрибутов текущего выделения форматирования символов.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, которая содержит символ форматирования атрибуты текущего выделенного фрагмента.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) сообщений и [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>CRichEditView::GetClipboardData  
 Эта функция вызывается как часть обработки [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315).  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>Параметры  
 `lpchrg`  
 Указатель на [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структуры определения диапазона символов (и элементы OLE) для копирования данных объекта, заданного параметром `lplpdataobj`.  
  
 `dwReco`  
 Флаг операции в буфер обмена. Может принимать одно из следующих значений.  
  
- **RECO_COPY** копирование в буфер обмена.  
  
- **RECO_CUT** Вырезать в буфер обмена.  
  
- **RECO_DRAG** (перетаскивание мышью) операции перетаскивания.  
  
- **RECO_DROP** (перетаскивание мышью) операция перетаскивания.  
  
- **RECO_PASTE** вставить из буфера обмена.  
  
 `lpRichDataObj`  
 Указатель на [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) изменить объект, содержащий данные из буфера обмена с широкими возможностями управления ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 Указатель на переменную указатель, получающий адрес `IDataObject` объект, представляющий диапазон, указанный в `lpchrg` параметр. Значение `lplpdataobj` учитывается, если возвращается сообщение об ошибке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение успехом операции. Дополнительные сведения о `HRESULT`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение указывает на успешное завершение, **IRichEditOleCallback::GetClipboardData** возвращает `IDataObject` осуществляется `lplpdataobj`; в противном случае, он возвращает осуществляется из них `lpRichDataObj`. Переопределите эту функцию, чтобы указать собственные данные в буфер обмена. Реализация по умолчанию эта функция возвращает **E_NOTIMPL**.  
  
 Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), и [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] и [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="getcontextmenu"></a>CRichEditView::GetContextMenu  
 Эта функция вызывается как часть обработки [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317).  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>Параметры  
 *seltyp*  
 Тип выбора. Выбор типа значения описаны в разделе «Примечания».  
  
 `lpoleobj`  
 Указатель на **OLEOBJECT** структура, задающая первый выбранный объект OLE, если выделение содержит один или несколько элементов OLE. Если выбор не содержит элементов, `lpoleobj` — **NULL**. **OLEOBJECT** структура содержит указатель в объект OLE v таблицу.  
  
 `lpchrg`  
 Указатель на [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) структура, содержащая текущее выделение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор в контекстном меню.  
  
### <a name="remarks"></a>Примечания  
 Эта функция является обычной частью правой кнопки мыши вниз обработки.  
  
 Выбор типа может быть любое сочетание следующих флагов:  
  
- `SEL_EMPTY`Указывает, что не выделен текущей.  
  
- `SEL_TEXT`Указывает, что текущее выделение содержит текст.  
  
- `SEL_OBJECT`Указывает, что текущее выделение содержит по крайней мере один элемент OLE.  
  
- `SEL_MULTICHAR`Указывает, что текущее выделение содержит более одного символа в тексте.  
  
- `SEL_MULTIOBJECT`Указывает, что текущее выделение содержит более одного объекта OLE.  
  
 Реализация по умолчанию возвращает **NULL**. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) и [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о **OLEOBJECT** типа, см. в статье OLE структуры и данных структуры распределения в *OLE базы знаний Майкрософт*.  
  
##  <a name="getdocument"></a>CRichEditView::GetDocument  
 Эта функция вызывается для получения указателя на `CRichEditDoc` связанный с этим представлением.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) объект, связанный с вашей `CRichEditView` объекта.  
  
##  <a name="getinplaceactiveitem"></a>CRichEditView::GetInPlaceActiveItem  
 Вызов эту функцию для получения OLE элемент, который в настоящее время активации на месте в этом `CRichEditView` объекта.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на одном месте, в active [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объект в этом представлении форматируемого; **NULL** Если отсутствует элемент OLE в данный момент в активном состоянии на месте.  
  
##  <a name="getmargins"></a>CRichEditView::GetMargins  
 Эта функция вызывается для получения текущего поля, используемые в печати.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поля, используемые в печати, измеряется в `MM_TWIPS`.  
  
##  <a name="getpagerect"></a>CRichEditView::GetPageRect  
 Эта функция вызывается для получения размеров страницы, используемые в печати.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Границы страницы, используемые в печати, измеряется в `MM_TWIPS`.  
  
### <a name="remarks"></a>Примечания  
 Это значение зависит от размера бумаги.  
  
##  <a name="getpapersize"></a>CRichEditView::GetPaperSize  
 Эта функция вызывается для получения текущего размера бумаги.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер бумаги, используемые в печати, измеряется в `MM_TWIPS`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#153;](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>CRichEditView::GetParaFormatSelection  
 Эта функция вызывается для получения атрибуты текущего выделения форматирования абзаца.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) структуру, содержащую атрибуты текущего выделения форматирования абзаца.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) сообщений и [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getprintrect"></a>CRichEditView::GetPrintRect  
 Эта функция вызывается для получения границы области печати страницы прямоугольника.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Границы области изображения, используемые в печати, измеряется в `MM_TWIPS`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#154;](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>CRichEditView::GetPrintWidth  
 Эта функция вызывается для определения ширины области печати.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина области печати измеряется в `MM_TWIPS`.  
  
##  <a name="getricheditctrl"></a>CRichEditView::GetRichEditCtrl  
 Эта функция вызывается для получения [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) объекта, связанного с `CRichEditView` объекта.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CRichEditCtrl` Объекта для этого представления.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::FindText](#findtext).  
  
##  <a name="getselecteditem"></a>CRichEditView::GetSelectedItem  
 Эта функция вызывается для получения объекта OLE ( `CRichEditCntrItem` объектов) в данный момент выбран в этом `CRichEditView` объекта.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объекта, выбранного в `CRichEditView` объекта; **NULL** Если элемент не выбран в этом представлении.  
  
##  <a name="gettextlength"></a>CRichEditView::GetTextLength  
 Эта функция вызывается для получения длины текста в этом `CRichEditView` объекта.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина текста в этом `CRichEditView` объекта.  
  
##  <a name="gettextlengthex"></a>CRichEditView::GetTextLengthEx  
 Вызов этой функции-члена для вычисления длины текста в этом `CRichEditView` объекта.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Значение, указывающее метод, используемый для определения длины текста. Этот член может быть один или несколько значений, перечисленных в член флаги [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `uCodePage`  
 Кодовая страница для перевода (CP_ACP для кодовой страницы ANSI, 1200 для Юникода).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов или байтов в элементе управления. Если были установлены несовместимые флаги `dwFlags`, эта функция-член возвращает `E_INVALIDARG`.  
  
### <a name="remarks"></a>Примечания  
 `GetTextLengthEx`предоставляет дополнительные способы определения длины текста. Он поддерживает 2.0 Изменить расширенные функциональные возможности. Дополнительные сведения см. в разделе [о широкие возможности изменять элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb787873) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="insertfileasobject"></a>CRichEditView::InsertFileAsObject  
 Эта функция вызывается для вставки в указанный файл (как [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объектов) в обширную изменить представление.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, содержащая имя файла для вставки.  
  
##  <a name="insertitem"></a>CRichEditView::InsertItem  
 Эта функция вызывается для вставки [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) объект в представление широкими возможностями редактирования.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель для вставляемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение, указывающее на успешное вставки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о `HRESULT`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isricheditformat"></a>CRichEditView::IsRichEditFormat  
 Эта функция вызывается для определения `cf` — это формат буфера обмена, текст, форматированный текст или форматированный текст с OLE-элементы.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 Формат буфера обмена интерес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `cf` является форматированного текста или правки формат буфера обмена.  
  
##  <a name="isselected"></a>CRichEditView::IsSelected  
 Эта функция вызывается для определения выбранного в данный момент в этом представлении указанного объекта OLE.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pDocItem`  
 Указатель на объект в представлении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект выделен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если другой метод для обработки выбора элементов OLE класс производным представлением.  
  
##  <a name="m_nbulletindent"></a>CRichEditView::m_nBulletIndent  
 Отступ для элементов маркированного списка в список. по умолчанию 720 единицы-1/2 дюйма.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>CRichEditView::m_nWordWrap  
 Указывает тип для этого представления форматируемого перенос по словам.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Примечания  
 Одно из следующих значений:  
  
- `WrapNone`Указывает не автоматический перенос.  
  
- `WrapToWindow`Указывает, перенос слов, исходя из ширины окна.  
  
- `WrapToTargetDevice`Указывает, перенос слов на основе характеристик целевого устройства.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::WrapChanged](#wrapchanged).  
  
##  <a name="onchareffect"></a>CRichEditView::OnCharEffect  
 Эта функция вызывается для переключения символ форматирования эффекты для текущего выделения.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `dwMask`  
 Форматирование знаков с эффектами для изменения текущей выделенной области.  
  
 `dwEffect`  
 Требуемый список эффектов для переключения форматирование знаков.  
  
### <a name="remarks"></a>Примечания  
 Каждый вызов этой функции переключает указанного эффекты форматирования для текущего выделения.  
  
 Дополнительные сведения о `dwMask` и `dwEffect` параметры и их возможные значения соответствующим членам данных в разделе [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#155;](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>CRichEditView::OnFindNext  
 Вызывается инфраструктурой при обработке команды из диалогового окна поиска и замены.  
  
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
 Направление поиска: **TRUE** указывает вниз; **FALSE**, up.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, является ли поиск совпадения слов целиком только или нет.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для поиска текста в `CRichEditView`. Переопределите эту функцию для изменения характеристик поиска для класса производным представлением.  
  
##  <a name="oninitialupdate"></a>CRichEditView::OnInitialUpdate  
 Вызывается платформой после представления впервые присоединяется к документу, но до первоначального отображения представления.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) функции-члена без указания информации (то есть, используя значения по умолчанию 0 `lHint` параметр и **NULL** для `pHint` параметр). Переопределите эту функцию, чтобы выполнить однократную инициализацию, которая требует сведений о документе. Например если приложение содержит документы фиксированного размера, можно использовать эту функцию для инициализации представления прокрутки ограничения, исходя из размера документа. Если приложение поддерживает документы переменного размера, используйте `OnUpdate` обновление прокрутки ограничивает каждый раз изменения документа.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::m_nWordWrap](#m_nwordwrap).  
  
##  <a name="onpastenativeobject"></a>CRichEditView::OnPasteNativeObject  
 Используйте эту функцию для загрузки данных в собственном из встроенного элемента.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>Параметры  
 *lpStg*  
 Указатель на [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, это делается путем создания [COleStreamFile](../../mfc/reference/colestreamfile-class.md) вокруг `IStorage`. `COleStreamFile` Можно прикрепить к архив и [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) вызывается для загрузки данных.  
  
 Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onparaalign"></a>CRichEditView::OnParaAlign  
 Эта функция используется для изменения выравнивания абзаца для выделенных абзацев.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>Параметры  
 `wAlign`  
 Требуемое выравнивание абзаца. Одно из следующих значений:  
  
- `PFA_LEFT`Выравнивание абзацев по левой границе.  
  
- `PFA_RIGHT`Выравнивание абзацев с правого поля.  
  
- `PFA_CENTER`Выравнивание по центру абзацев между полями.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#156;](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>CRichEditView::OnPrinterChanged  
 Переопределите эту функцию, чтобы изменить характеристики представления форматируемого при изменении принтера.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>Параметры  
 `dcPrinter`  
 Объект [CDC](../../mfc/reference/cdc-class.md) объекта для нового принтера.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает размер бумаги для физического высоту и ширину устройство вывода (принтер). При наличии контекст устройства, не связанных с `dcPrinter`, реализация по умолчанию задается размер бумаги 8,5 х 11 дюймов.  
  
##  <a name="onreplaceall"></a>CRichEditView::OnReplaceAll  
 Вызывается инфраструктурой при обработке заменить все команды из диалогового окна «Заменить».  
  
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
 Эта функция вызывается для замены всех вхождений данной текст на другую строку. Переопределите эту функцию, чтобы изменить параметры поиска для данного представления.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::FindText](#findtext).  
  
##  <a name="onreplacesel"></a>CRichEditView::OnReplaceSel  
 Вызывается инфраструктурой при обработке команды Replace из диалогового окна «Заменить».  
  
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
 Указывает направление поиска: **TRUE** не работает; **FALSE**, up.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра.  
  
 `bWord`  
 Указывает, если поиск необходимо выбрать слова целиком или нет.  
  
 `lpszReplace`  
 Текст замены.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для замены одного вхождения заданного текст на другую строку. Переопределите эту функцию, чтобы изменить параметры поиска для данного представления.  
  
##  <a name="ontextnotfound"></a>CRichEditView::OnTextNotFound  
 Вызывается платформой, если поиск заканчивается неудачей.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который не был найден.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для изменения вывода уведомлений от [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356).  
  
 Дополнительные сведения см. в разделе [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#157;](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>CRichEditView::OnUpdateCharEffect  
 Платформа вызывает эту функцию, чтобы обновить командный пользовательский Интерфейс для команд эффект символов.  
  
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
 Указывает символ маску форматирования.  
  
 `dwEffect`  
 Указывает символ форматирования эффект.  
  
### <a name="remarks"></a>Примечания  
 Маска `dwMask` указывает, какой знак атрибуты форматирования для проверки. Флаги `dwEffect` список атрибутов для набора или очистить форматирования символов.  
  
 Дополнительные сведения о `dwMask` и `dwEffect` параметры и их возможные значения соответствующим членам данных в разделе [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#158;](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>CRichEditView::OnUpdateParaAlign  
 Платформа вызывает эту функцию, чтобы обновить командный пользовательский Интерфейс для команд эффект абзаца.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта.  
  
 `wAlign`  
 Чтобы проверить выравнивание абзаца. Одно из следующих значений:  
  
- `PFA_LEFT`Выравнивание абзацев по левой границе.  
  
- `PFA_RIGHT`Выравнивание абзацев с правого поля.  
  
- `PFA_CENTER`Выравнивание по центру абзацев между полями.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#159;](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>CRichEditView::PrintInsideRect  
 Эта функция вызывается для форматирования диапазон текста в элементе управления "rich edit" в соответствии с размерами *rectLayout* для устройства, заданного в `pDC`.  
  
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
 [RECT](../../mfc/reference/rect-structure1.md) или [CRect](../../atl-mfc-shared/reference/crect-class.md) определяет области вывода.  
  
 `nIndexStart`  
 Отсчитываемый от нуля индекс первого символа для форматирования.  
  
 `nIndexStop`  
 Отсчитываемый от нуля индекс последнего символа для форматирования.  
  
 *bOutput*  
 Указывает, если текст должен отображаться. Если **FALSE**, просто измеряется текст.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс последнего символа, который помещается в области вывода, плюс один.  
  
### <a name="remarks"></a>Примечания  
 Как правило, этот вызов сопровождается вызов [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) создающий выходные данные.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="printpage"></a>CRichEditView::PrintPage  
 Эта функция вызывается для форматирования диапазон текста в элементе управления rich edit для устройства вывода, заданные `pDC`.  
  
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
 Индекс последнего символа, которое может уместиться на странице плюс один.  
  
### <a name="remarks"></a>Примечания  
 Макет для каждой страницы управляется [GetPageRect](#getpagerect) и [GetPrintRect](#getprintrect). Как правило, этот вызов сопровождается вызов [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) создающий выходные данные.  
  
 Обратите внимание, что поля относятся к физической страницы, не логической страницы. Таким образом поля нулевой часто клипов текст, так как многие принтеры имеют области печати страницы. Во избежание обрезки текста, следует вызвать [SetMargins](#setmargins) и задать разумное поля перед печатью.  
  
##  <a name="queryacceptdata"></a>CRichEditView::QueryAcceptData  
 Вызывается платформой для вставки в форматируемого объекта.  
  
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
 Указывает, если операция вставки следует продолжить или нет.  
  
 `hMetaFile`  
 Дескриптор метафайла, используемую для рисования на значок элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение успехом операции.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обработки другой организации COM элементов в документ производного класса. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения о `HRESULT` и `IDataObject`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) и [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), соответственно, в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#160;](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>CRichEditView::SetCharFormat  
 Вызовите эту функцию для задания атрибутов для нового текста в этом форматирования символов `CRichEditView` объекта.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) структуру, содержащую новых атрибутов форматирования символов по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Только атрибуты, указанные в **dwMask** членом `cf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) сообщений и [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#152;](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>CRichEditView::SetMargins  
 Эта функция вызывается для задания печати полей форматируемого представления.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>Параметры  
 *rectMargin*  
 Новые значения полей для печати, измеряется в `MM_TWIPS`.  
  
### <a name="remarks"></a>Примечания  
 Если [m_nWordWrap](#m_nwordwrap) — `WrapToTargetDevice`, следует вызвать [WrapChanged](#wrapchanged) после использования этой функции для настройки печати характеристики.  
  
 Обратите внимание, что используемые поля [PrintPage](#printpage) относительны физической страницы, не логической страницы. Таким образом поля нулевой часто клипов текст, так как многие принтеры имеют области печати страницы. Во избежание обрезки текста, следует вызвать использование `SetMargins` задание полей разумного принтера перед печатью.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::GetPaperSize](#getpapersize).  
  
##  <a name="setpapersize"></a>CRichEditView::SetPaperSize  
 Эта функция вызывается для задания размера бумаги для печати этого представления форматируемого.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>Параметры  
 *sizePaper*  
 Новые значения размера бумаги для печати, измеряется в `MM_TWIPS`.  
  
### <a name="remarks"></a>Примечания  
 Если [m_nWordWrap](#m_nwordwrap) — `WrapToTargetDevice`, следует вызвать [WrapChanged](#wrapchanged) после использования этой функции для настройки печати характеристики.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#161;](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditView::SetParaFormat  
 Вызывайте эту функцию, чтобы задать атрибуты для текущего выбора в этом форматирования абзаца `CRichEditView` объекта.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Параметры  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) атрибуты форматирования абзаца структура, содержащая новое значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только атрибуты, указанные в **dwMask** членом `pf` были изменены с помощью этой функции.  
  
 Дополнительные сведения см. в разделе [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) сообщений и [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#162;](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>CRichEditView::TextNotFound  
 Эта функция вызывается для сброса состояния внутреннего поиска [CRichEditView](../../mfc/reference/cricheditview-class.md) управления после сбоя вызова [строки FindText](#findtext).  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Содержит текстовую строку, не найден.  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется иметь что этот метод вызывается сразу после неудачных вызовов [строки FindText](#findtext) , чтобы правильно сбрасывается состояние внутреннего поиска элемента управления.  
  
 `lpszFind` Параметр должен включать одинаковое содержимое строка, предоставленная для [строки FindText](#findtext). После сброса состояния внутреннего поиска, этот метод будет вызывать [OnTextNotFound](#ontextnotfound) метод со строкой поиска указанных.  
  
### <a name="example"></a>Пример  
  В примере показано [CRichEditView::FindText](#findtext).  
  
##  <a name="wrapchanged"></a>CRichEditView::WrapChanged  
 Эта функция вызывается при изменении параметров печати ( [SetMargins](#setmargins) или [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределение эту функцию, чтобы изменить способ обширного изменить представление реагирует на изменения в [m_nWordWrap](#m_nwordwrap) или характеристики печати ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#163;](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-класс](../../mfc/reference/cricheditdoc-class.md)   
 [Класс CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)

