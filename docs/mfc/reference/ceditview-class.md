---
title: Класс CEditView | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b15d604670ec1c458c6ca8db5b3b4eab51fb8f65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|[CEditView::GetBufferLength](#getbufferlength)|Получает длину буфера символов.|  
|[CEditView::GetEditCtrl](#geteditctrl)|Предоставляет доступ к `CEdit` часть `CEditView` объекта (Windows редактирование элемента управления).|  
|[CEditView::GetPrinterFont](#getprinterfont)|Извлекает текущий шрифт принтера.|  
|[CEditView::GetSelectedText](#getselectedtext)|Извлекает текущее выделение текста.|  
|[CEditView::LockBuffer](#lockbuffer)|Блокирует буфер.|  
|[CEditView::PrintInsideRect](#printinsiderect)|Отрисовывает текст внутри заданного прямоугольника.|  
|[CEditView::SerializeRaw](#serializeraw)|Сериализует `CEditView` объекта на диске как обычный текст.|  
|[CEditView::SetPrinterFont](#setprinterfont)|Задает новый шрифт принтера.|  
|[CEditView::SetTabStops](#settabstops)|Задает позиции табуляции для отображения на экране и печати.|  
|[CEditView::UnlockBuffer](#unlockbuffer)|Разблокирует буфер.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|Находит следующее вхождение строки текста.|  
|[CEditView::OnReplaceAll](#onreplaceall)|Заменяет все вхождения заданной строки новую строку.|  
|[CEditView::OnReplaceSel](#onreplacesel)|Заменяет текущее выделение.|  
|[CEditView::OnTextNotFound](#ontextnotfound)|Вызывается, когда не удается сопоставить дальнейшей текст операции поиска.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|По умолчанию стиль для объектов типа **CEditView.**|  
  
## <a name="remarks"></a>Примечания  
 `CEditView` Класс предоставляет следующие дополнительные функции:  
  
-   Печать.  
  
-   Поиск и замена.  
  
 Поскольку класс `CEditView` является производным от класса `CView`, объекты класса `CEditView` можно использовать с документами и шаблонами документов.  
  
 Каждый `CEditView` текст элемента управления сохраняется в свой собственный объект глобальной памяти. Приложение может иметь любое количество `CEditView` объектов.  
  
 Создание объектов типа `CEditView` окна редактирования с дополнительными функциональными возможностями, перечисленных выше, или если требуется использовать возможности простого текстового редактора. Объект `CEditView` объект может находиться всей клиентской области окна. Создавать собственные производные классы из `CEditView` для добавления или изменения основные функциональные возможности или объявления классов, которые могут быть добавлены в шаблон документа.  
  
 Реализация по умолчанию класса `CEditView` обрабатывает следующие команды: **ID_EDIT_SELECT_ALL**, **ID_EDIT_FIND**, **ID_EDIT_REPLACE**, **ID_EDIT_REPEAT**, и **ID_FILE_PRINT**.  
  
 Максимальное количество знаков по умолчанию для `CEditView` — (1024 \* 1048575 = 1024-1). Это можно изменить с помощью вызова **EM_LIMITTEXT** функция базового элемента управления edit. Однако ограничения различаются в зависимости от операционной системы и тип изменения элемента управления (в одном или многострочной). Дополнительные сведения об этих ограничениях см. в разделе [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Это ограничение можно изменить в элементе управления, переопределите `OnCreate()` работать для вашего `CEditView` класса и вставьте следующий код:  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 Объекты типа `CEditView` (или типов, производных от `CEditView`) имеют следующие ограничения:  
  
- `CEditView` не реализует true отображается вы получаете редактирования (WYSIWYG). Там, где есть выбор между удобочитаемость на экране и сопоставления вывода на печать, `CEditView` opts для удобства чтения с экрана.  
  
- `CEditView` для отображения текста в один шрифт. Форматирование специальных символов не поддерживается. См. класс [CRichEditView](../../mfc/reference/cricheditview-class.md) больше возможностей.  
  
-   Объем текста `CEditView` может содержать ограничено. Ограничения являются одинаковыми как для `CEdit` элемента управления.  
  
 Дополнительные сведения о `CEditView`, в разделе [производный представление классов доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
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
 После создания объекта, необходимо вызвать [CWnd::Create](../../mfc/reference/cwnd-class.md#create) функции, прежде чем использовать элемент управления для редактирования. Если производный класс `CEditView` и добавить его в шаблон с помощью `CWinApp::AddDocTemplate`, платформа вызывает этот конструктор обоих и **создать** функции.  
  
##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault  
 Содержит стиль по умолчанию `CEditView` объекта.  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>Примечания  
 Передайте этот статический член как `dwStyle` параметр **создать** функции для получения стиль по умолчанию для `CEditView` объекта.  
  
##  <a name="findtext"></a>  CEditView::FindText  
 Вызовите `FindText` функция поиска `CEditView` буфер текста объекта.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bNext = TRUE,  
    BOOL bCase = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который требуется найти.  
  
 `bNext`  
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска находится ближе к началу буфера.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, поиск с учетом регистра. Если **FALSE**, поиск выполняется без учета регистра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден текст для поиска; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняет поиск текста в буфере для текст, заданный параметром `lpszFind`, начиная с текущего выделения в направлении, указанным `bNext`и чувствительность к регистру, определяемое `bCase`. Если текст найден, он задает возможности выбора, чтобы этот текст и возвращает ненулевое значение. Если текст не найден, функция возвращает значение 0.  
  
 Обычно не требуется для вызова `FindText` работать, если не переопределено `OnFindNext`, который вызывает `FindText`.  
  
##  <a name="getbufferlength"></a>  CEditView::GetBufferLength  
 Вызовите эту функцию-член, чтобы получить номер символов в данный момент в буфере поля ввода, не включая завершающий символ null.  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки в буфере.  
  
##  <a name="geteditctrl"></a>  CEditView::GetEditCtrl  
 Вызовите `GetEditCtrl` для получения ссылки на поле редактирования, используемый представления изменения.  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект `CEdit`.  
  
### <a name="remarks"></a>Примечания  
 Этот элемент управления имеет тип [CEdit](../../mfc/reference/cedit-class.md), поэтому можно работать напрямую с помощью элемента управления редактирования Windows `CEdit` функции-члены.  
  
> [!CAUTION]
>  С помощью `CEdit` объекта можно изменить изменение состояния окон базового элемента управления. Например, не следует изменять параметры табуляции, с помощью [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) работать, поскольку `CEditView` кэширует эти параметры для использования в элементе управления, а также при печати. Вместо этого используйте [CEditView::SetTabStops](#settabstops).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont  
 Вызовите `GetPrinterFont` для получения указателя на [CFont](../../mfc/reference/cfont-class.md) , описывающий текущий шрифт принтера.  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CFont` , указывающий текущий шрифт принтера; **NULL** Если шрифт принтера не задано. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.  
  
### <a name="remarks"></a>Примечания  
 Если шрифт принтера не задан, печати поведение по умолчанию `CEditView` класс является будет печататься шрифтом, который используется для отображения.  
  
 Эта функция используется для определения текущего шрифта принтера. Если не шрифта нужный принтер, используйте [CEditView::SetPrinterFont](#setprinterfont) изменить его.  
  
##  <a name="getselectedtext"></a>  CEditView::GetSelectedText  
 Вызовите `GetSelectedText` копирование выбранного текста в `CString` объекта до конца строки выбранного или символ, предшествующий первого символа возврата каретки в выделенном фрагменте.  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strResult`  
 Ссылку на `CString` объекта, который должен получить выделенный текст.  
  
##  <a name="lockbuffer"></a>  CEditView::LockBuffer  
 Вызовите эту функцию-член для получения указателя на буфер. Не следует изменять размер буфера.  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер поле редактирования.  
  
##  <a name="onfindnext"></a>  CEditView::OnFindNext  
 Выполняет поиск текста в буфере для текст, заданный параметром `lpszFind`, в направлении, указанным `bNext`, учитывающей регистр, определяемое `bCase`.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который требуется найти.  
  
 `bNext`  
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска находится ближе к началу буфера.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, поиск с учетом регистра. Если **FALSE**, поиск выполняется без учета регистра.  
  
### <a name="remarks"></a>Примечания  
 Поиск начинается с начала текущего выделения и достигается посредством вызова [строки FindText](#findtext). В реализации по умолчанию `OnFindNext` вызовы [OnTextNotFound](#ontextnotfound) Если текст не найден.  
  
 Переопределить `OnFindNext` для изменения способа `CEditView`-производного объекта ищет текст. `CEditView` вызовы `OnFindNext` , когда пользователь нажмет кнопку Найти далее в стандартном диалоговом окне поиска.  
  
##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll  
 `CEditView` вызовы `OnReplaceAll` при выборе пользователем кнопки «Заменить все» в стандартное диалоговое окно замены.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который требуется найти.  
  
 `lpszReplace`  
 Текст, замещающий текст для поиска.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, поиск с учетом регистра. Если **FALSE**, поиск выполняется без учета регистра.  
  
### <a name="remarks"></a>Примечания  
 `OnReplaceAll` выполняет поиск текста в буфере для текст, заданный параметром `lpszFind`, учитывающей регистр, определяемое `bCase`. Поиск начинается с начала текущего выделения. Каждый раз при обнаружении поиска текста, эта функция заменяет это вхождение текста, текст, заданный параметром `lpszReplace`. Поиск выполняется с помощью вызова [строки FindText](#findtext). В реализации по умолчанию [OnTextNotFound](#ontextnotfound) вызывается, если текст не найден.  
  
 Если текущее выделение не соответствует `lpszFind`, выбор обновляется до первого вхождения текст, заданный параметром `lpszFind` и замены не выполняется. Это позволяет убедиться, что они должны делать, если выделение не соответствует заменяемый текст.  
  
 Переопределить `OnReplaceAll` для изменения способа `CEditView`-производного объекта заменяет текст.  
  
##  <a name="onreplacesel"></a>  CEditView::OnReplaceSel  
 `CEditView` вызовы `OnReplaceSel` когда пользователь выбирает кнопку «Заменить» в стандартное диалоговое окно замены.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который требуется найти.  
  
 `bNext`  
 Указывает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска находится ближе к началу буфера.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, поиск с учетом регистра. Если **FALSE**, поиск выполняется без учета регистра.  
  
 `lpszReplace`  
 Текст, чтобы заменить найденный текст.  
  
### <a name="remarks"></a>Примечания  
 После замены выделение, эта функция осуществляет текст в буфер для следующего вхождения текста, указанного по `lpszFind`, в направлении, указанным `bNext`, учитывающей регистр, определяемое `bCase`. Поиск выполняется с помощью вызова [строки FindText](#findtext). Если текст не найден, [OnTextNotFound](#ontextnotfound) вызывается.  
  
 Переопределить `OnReplaceSel` для изменения способа `CEditView`-производного объекта заменяет выделенный текст.  
  
##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound  
 Переопределить эту функцию, чтобы изменить реализацию по умолчанию, который вызывает функции Windows **MessageBeep**.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который требуется найти.  
  
##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect  
 Вызовите `PrintInsideRect` печать текста в прямоугольник, задаваемый параметром *rectLayout*.  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства принтера.  
  
 *rectLayout*  
 Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [структура RECT](../../mfc/reference/rect-structure1.md) указание прямоугольник, в котором будет отображаться текст.  
  
 `nIndexStart`  
 Индекс в буфере первый символ должен быть подготовлен к просмотру.  
  
 `nIndexStop`  
 Индекс в буфере символа после последнего символа, который должен быть подготовлен к просмотру.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс следующий символ для печати (то есть символ после последнего символа к просмотру).  
  
### <a name="remarks"></a>Примечания  
 Если `CEditView` управления не имеет стиль **ES_AUTOHSCROLL**, текст переносится в прямоугольнике подготовки к просмотру. Если элемент управления со стилем **ES_AUTOHSCROLL**, текст будет обрезан у правого края прямоугольника.  
  
 **Rect.bottom** элемент *rectLayout* объекта изменено таким образом, измерения прямоугольника определяют часть исходного прямоугольника, занятую текст.  
  
##  <a name="serializeraw"></a>  CEditView::SerializeRaw  
 Вызовите `SerializeRaw` иметь `CArchive` объект чтения или записи текста `CEditView` объекта в текстовый файл.  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Ссылка на `CArchive` объект, который хранит сериализованные текст.  
  
### <a name="remarks"></a>Примечания  
 `SerializeRaw` отличается от `CEditView`его внутренней реализации `Serialize` , поскольку она считывает и записывает только текст, без предшествующих описание объекта данных.  
  
##  <a name="setprinterfont"></a>  CEditView::SetPrinterFont  
 Вызовите `SetPrinterFont` для задания шрифта принтера для шрифта, указанного `pFont`.  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 `pFont`  
 Указатель на объект типа `CFont`. Если **NULL**, шрифт, используемый для печати зависит от шрифт.  
  
### <a name="remarks"></a>Примечания  
 Если требуется, чтобы представление, чтобы всегда использовать определенный шрифт для печати, включите вызов `SetPrinterFont` в вашем классе `OnPreparePrinting` функции. Это виртуальная функция вызывается перед печатью, чтобы изменить шрифт выполняется до использования выводится содержимое представления.  
  
##  <a name="settabstops"></a>  CEditView::SetTabStops  
 Вызывайте эту функцию, чтобы установить позицию табуляции, используемый для отображения и печати.  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>Параметры  
 `nTabStops`  
 Ширина каждой позиции табуляции в диалоговых единицах.  
  
### <a name="remarks"></a>Примечания  
 Поддерживается только один ширину табуляции. ( `CEdit` объекты поддерживают несколько ширину вкладок.) Ширина, в единицах диалогового окна, которое равно одной четвертой Средняя ширина символа (с учетом прописных и строчных букв только) шрифта, используемого во время печати или отображении. Не следует использовать `CEdit::SetTabStops` из-за `CEditView` необходимо кэшировать значение табуляции.  
  
 Эта функция изменяет только вкладки объекта, для которого он вызван. Для изменения вкладке останавливает для каждого `CEditView` объекта в приложении, вызывать каждый объект `SetTabStops` функции.  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода задает позиции табуляции в элементе управления для каждого четвертый символ тщательно Измеряя шрифт, который использует элемент управления.  
  
 [!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer  
 Вызовите эту функцию-член разблокировать буфер.  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите `UnlockBuffer` после завершения использования указатель, возвращенный [LockBuffer](#lockbuffer).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC SUPERPAD](../../visual-cpp-samples.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Класс CRichEditView](../../mfc/reference/cricheditview-class.md)
