---
title: "Класс CEditView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEditView
dev_langs:
- C++
helpviewer_keywords:
- text editors, CEditView class
- text editors
- edit controls, classes
- views, classes
- CEditView class
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
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
ms.openlocfilehash: 688a6c0e871a9456b85a8ed02ce43d7fa9ca8180
ms.lasthandoff: 02/24/2017

---
# <a name="ceditview-class"></a>Класс CEditView
Тип класса представления, который предоставляет функциональные возможности элемента управления "поле ввода" Windows и может использоваться для реализации простой функциональности текстового редактора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CEditView : public CCtrlView  
```  
  
## <a name="members"></a>Члены  
  
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
|[CEditView::GetSelectedText](#getselectedtext)|Получает текущее выделение текста.|  
|[CEditView::LockBuffer](#lockbuffer)|Блокирует буфер.|  
|[CEditView::PrintInsideRect](#printinsiderect)|Отображает текст внутри данного прямоугольника.|  
|[CEditView::SerializeRaw](#serializeraw)|Сериализует `CEditView` объекта на диск как обычный текст.|  
|[CEditView::SetPrinterFont](#setprinterfont)|Задает новый шрифт принтера.|  
|[CEditView::SetTabStops](#settabstops)|Задает позиции табуляции для изображения на экране и печати.|  
|[CEditView::UnlockBuffer](#unlockbuffer)|Разблокирует буфер.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|Находит следующее вхождение строки текста.|  
|[CEditView::OnReplaceAll](#onreplaceall)|Заменяет все вхождения заданной строки с новой строки.|  
|[CEditView::OnReplaceSel](#onreplacesel)|Заменяет текущее выделение.|  
|[CEditView::OnTextNotFound](#ontextnotfound)|Вызывается, когда не удается сопоставить любой текст, дополнительные операции поиска.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|По умолчанию стиль для объектов типа **CEditView.**|  
  
## <a name="remarks"></a>Примечания  
 `CEditView` Класс предоставляет следующие дополнительные функции:  
  
-   Печать.  
  
-   Поиск и замена.  
  
 Поскольку класс `CEditView` является производным от класса `CView`, объекты класса `CEditView` можно использовать с документами и шаблонами документов.  
  
 Каждый `CEditView` текст элемента управления сохраняется в объекте глобальной памяти. Приложение может иметь любое количество `CEditView` объектов.  
  
 Создание объектов типа `CEditView` окна редактирования с дополнительными функциональными возможностями, перечисленных выше, или если требуется использовать возможности простого текстового редактора. Объект `CEditView` объект может занимать всю клиентскую область окна. Создавать собственные производные классы от `CEditView` для добавления или изменения основные функциональные возможности или объявления классов, которые могут быть добавлены в шаблон документа.  
  
 Реализация по умолчанию класса `CEditView` обрабатывает следующие команды: **ID_EDIT_SELECT_ALL**, **ID_EDIT_FIND**, **ID_EDIT_REPLACE**, **ID_EDIT_REPEAT**, и **ID_FILE_PRINT**.  
  
 Максимальное количество знаков по умолчанию для `CEditView` — (1024 \* 1048575 = 1024-1). Это можно изменить с помощью вызова **EM_LIMITTEXT** функция базовый элемент управления. Однако ограничения различаются в зависимости от операционной системы и изменить тип элемента управления (в одном или многострочный). Дополнительные сведения об этих ограничениях см. в разделе [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Чтобы изменить это ограничение в элементе управления, переопределите `OnCreate()` функции для вашего `CEditView` класса и вставьте следующую строку кода:  
  
 [!code-cpp[NVC_MFCDocView&#65;](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 Объекты типа `CEditView` (или типов, производных от `CEditView`) имеют следующие ограничения:  
  
- `CEditView`реализует true на экране отображается, вы получаете редактирования (WYSIWYG). Там, где есть выбор между удобочитаемость на экране и печати соответствующего `CEditView` позволяет использовать для удобства чтения с экрана.  
  
- `CEditView`для отображения текста в один шрифт. Форматирование специальных символов не поддерживается. См. класс [CRichEditView](../../mfc/reference/cricheditview-class.md) больше возможностей.  
  
-   Объем текста, `CEditView` может содержать ограничено. Ограничения являются одинаковыми как для `CEdit` элемента управления.  
  
 Дополнительные сведения о `CEditView`, в разделе [производный представление классов доступные в MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="a-nameceditviewa--ceditviewceditview"></a><a name="ceditview"></a>CEditView::CEditView  
 Создает объект типа `CEditView`.  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, необходимо вызвать [CWnd::Create](../../mfc/reference/cwnd-class.md#create) функцию, прежде чем использовать элемент управления для редактирования. При наследовании от класса `CEditView` и добавьте его в шаблон с помощью `CWinApp::AddDocTemplate`, платформа вызывает этот конструктор обоих и **создать** функции.  
  
##  <a name="a-namedwstyledefaulta--ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>CEditView::dwStyleDefault  
 Стиль по умолчанию содержит `CEditView` объекта.  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>Примечания  
 Передайте этот статический член как `dwStyle` параметр **создать** функции для получения стиль по умолчанию для `CEditView` объекта.  
  
##  <a name="a-namefindtexta--ceditviewfindtext"></a><a name="findtext"></a>CEditView::FindText  
 Вызов `FindText` для поиска `CEditView` объекта текстового буфера.  
  
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
 Задает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска — к началу буфера.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, при поиске не учитывается регистр. Если **FALSE**, поиск не учитывает регистр.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если искомый текст был найден. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняет поиск текста в буфере, текст, заданный параметром `lpszFind`, начиная с текущего выделения в направлении, указанным `bNext`и чувствительность к регистру, определяемое `bCase`. Если текст найден, он устанавливает выделение для найденного текста и возвращает ненулевое значение. Если текст не найден, функция возвращает значение 0.  
  
 Обычно не нужно вызывать `FindText` работать, если не переопределено `OnFindNext`, который вызывает метод `FindText`.  
  
##  <a name="a-namegetbufferlengtha--ceditviewgetbufferlength"></a><a name="getbufferlength"></a>CEditView::GetBufferLength  
 Вызовите эту функцию-член, чтобы получить количество символов в данный момент в буфере элемента управления поля ввода, не включая завершающий символ null.  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки в буфере.  
  
##  <a name="a-namegeteditctrla--ceditviewgeteditctrl"></a><a name="geteditctrl"></a>CEditView::GetEditCtrl  
 Вызов `GetEditCtrl` для получения ссылки на поле редактирования, используемый в представление редактирования.  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект `CEdit`.  
  
### <a name="remarks"></a>Примечания  
 Этот элемент управления имеет тип [CEdit](../../mfc/reference/cedit-class.md), поэтому можно работать напрямую с помощью элемента управления редактирования Windows `CEdit` функции-члены.  
  
> [!CAUTION]
>  С помощью `CEdit` объекта, измените состояние базового Windows можно изменить элемент управления. Например, не изменяйте параметры табуляции, с помощью [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) работать, поскольку `CEditView` кэширует эти параметры для использования в элементе управления, а также в печати. Вместо этого используйте [CEditView::SetTabStops](#settabstops).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#66;](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="a-namegetprinterfonta--ceditviewgetprinterfont"></a><a name="getprinterfont"></a>CEditView::GetPrinterFont  
 Вызов `GetPrinterFont` для получения указателя на [CFont](../../mfc/reference/cfont-class.md) , описывающий текущий шрифт принтера.  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CFont` объект, который указывает текущий шрифт принтера; **NULL** Если шрифт принтера не было задано. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.  
  
### <a name="remarks"></a>Примечания  
 Если шрифт принтера не было задано, печати поведение по умолчанию `CEditView` класс-печать с помощью того же шрифт, используемый для отображения.  
  
 Эта функция используется для определения текущего шрифта принтера. Если не шрифт нужный принтер, используйте [CEditView::SetPrinterFont](#setprinterfont) для его изменения.  
  
##  <a name="a-namegetselectedtexta--ceditviewgetselectedtext"></a><a name="getselectedtext"></a>CEditView::GetSelectedText  
 Вызов `GetSelectedText` копирование выбранного текста в `CString` объекта до конца выбранного или символ, перед первым символом возврата каретки в выделенной области.  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strResult`  
 Ссылку на `CString` объект, который должен получить выделенный текст.  
  
##  <a name="a-namelockbuffera--ceditviewlockbuffer"></a><a name="lockbuffer"></a>CEditView::LockBuffer  
 Вызовите эту функцию-член может получить указатель на буфер. Буфер не должно изменяться.  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер элемента управления поля ввода.  
  
##  <a name="a-nameonfindnexta--ceditviewonfindnext"></a><a name="onfindnext"></a>CEditView::OnFindNext  
 Выполняет поиск текста в буфере, текст, заданный параметром `lpszFind`, в направлении, указанным `bNext`, учитывающей регистр, определяемое `bCase`.  
  
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
 Задает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска — к началу буфера.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, при поиске не учитывается регистр. Если **FALSE**, поиск не учитывает регистр.  
  
### <a name="remarks"></a>Примечания  
 Поиск начинается с начала текущего выделенного фрагмента и осуществляется посредством вызова [строки FindText](#findtext). В реализации по умолчанию `OnFindNext` вызовов [OnTextNotFound](#ontextnotfound) Если текст не найден.  
  
 Переопределение `OnFindNext` изменить `CEditView`-производный объект выполняет поиск текста. `CEditView`вызовы `OnFindNext` когда пользователь нажимает кнопки Найти далее в стандартное диалоговое окно поиска.  
  
##  <a name="a-nameonreplacealla--ceditviewonreplaceall"></a><a name="onreplaceall"></a>CEditView::OnReplaceAll  
 `CEditView`вызовы `OnReplaceAll` при выборе пользователем кнопки «Заменить все» в диалоговом окне заменить стандартный.  
  
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
 Текст, чтобы заменить найденный текст.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, при поиске не учитывается регистр. Если **FALSE**, поиск не учитывает регистр.  
  
### <a name="remarks"></a>Примечания  
 `OnReplaceAll`выполняет поиск текста в буфере, текст, заданный параметром `lpszFind`, учитывающей регистр, определяемое `bCase`. Поиск начинается с начала текущего выделенного фрагмента. Каждый раз при обнаружении искомого текста, эта функция заменяет это вхождение текста, текст, заданный параметром `lpszReplace`. Поиск выполняется с помощью вызова [строки FindText](#findtext). В реализации по умолчанию [OnTextNotFound](#ontextnotfound) вызывается, если текст не найден.  
  
 Если текущее выделение не соответствует `lpszFind`, выбор обновляется до первого вхождения текст, заданный параметром `lpszFind` , что замена не выполняется. Это позволяет убедиться, что им нужно делать, если выбор не соответствует заменяемый текст.  
  
 Переопределение `OnReplaceAll` изменить `CEditView`-производный объект заменяет текст.  
  
##  <a name="a-nameonreplacesela--ceditviewonreplacesel"></a><a name="onreplacesel"></a>CEditView::OnReplaceSel  
 `CEditView`вызовы `OnReplaceSel` когда пользователь выбирает кнопку «Заменить» в диалоговом окне заменить стандартный.  
  
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
 Задает направление поиска. Если **TRUE**, направление поиска задается в конец буфера. Если **FALSE**, направление поиска — к началу буфера.  
  
 `bCase`  
 Указывает, является ли поиск с учетом регистра. Если **TRUE**, при поиске не учитывается регистр. Если **FALSE**, поиск не учитывает регистр.  
  
 `lpszReplace`  
 Текст, который заменяется найденный текст.  
  
### <a name="remarks"></a>Примечания  
 После замены выбора, эта функция выполняет текст в буфере следующего вхождения текста, указанного в `lpszFind`, в направлении, указанным `bNext`, учитывающей регистр, определяемое `bCase`. Поиск выполняется с помощью вызова [строки FindText](#findtext). Если текст не найден, [OnTextNotFound](#ontextnotfound) вызывается.  
  
 Переопределение `OnReplaceSel` изменить `CEditView`-производный объект заменяет выделенный текст.  
  
##  <a name="a-nameontextnotfounda--ceditviewontextnotfound"></a><a name="ontextnotfound"></a>CEditView::OnTextNotFound  
 Переопределить эту функцию, чтобы изменить реализацию по умолчанию, которая вызывает функцию Windows **MessageBeep**.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFind`  
 Текст, который требуется найти.  
  
##  <a name="a-nameprintinsiderecta--ceditviewprintinsiderect"></a><a name="printinsiderect"></a>CEditView::PrintInsideRect  
 Вызов `PrintInsideRect` печать текста в прямоугольник, задаваемый параметром *rectLayout*.  
  
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
 Индекс в буфере первый символ для отображения.  
  
 `nIndexStop`  
 Индекс в буфере символа после последнего символа к просмотру.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс следующий символ для печати (то есть следующий символ после последнего символа отображается).  
  
### <a name="remarks"></a>Примечания  
 Если `CEditView` управления не имеет стиль **ES_AUTOHSCROLL**, перенос текста выполняется отрисовка прямоугольника. Если элемент управления имеет стиль **ES_AUTOHSCROLL**, текст будет обрезан по правому краю прямоугольника.  
  
 **Rect.bottom** элемент *rectLayout* объекта изменяется таким образом, чтобы прямоугольник измерения определяют часть исходного прямоугольника, занятую текст.  
  
##  <a name="a-nameserializerawa--ceditviewserializeraw"></a><a name="serializeraw"></a>CEditView::SerializeRaw  
 Вызов `SerializeRaw` для `CArchive` объекта чтения или записи текста `CEditView` объекта в текстовый файл.  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Ссылка на `CArchive` объект, который хранит сериализованный текст.  
  
### <a name="remarks"></a>Примечания  
 `SerializeRaw`отличается от `CEditView`внутренняя реализация `Serialize` , поскольку она считывает и записывает только текст, без предшествующих описание объекта данных.  
  
##  <a name="a-namesetprinterfonta--ceditviewsetprinterfont"></a><a name="setprinterfont"></a>CEditView::SetPrinterFont  
 Вызов `SetPrinterFont` для задания шрифта принтера для шрифта, указанного `pFont`.  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 `pFont`  
 Указатель на объект типа `CFont`. Если **NULL**, шрифт, используемый для печати основана на шрифт.  
  
### <a name="remarks"></a>Примечания  
 Следует всегда использовать определенный шрифт для печати представления включают вызов `SetPrinterFont` в своем классе `OnPreparePrinting` функции. Это виртуальная функция вызывается, перед печатью, поэтому изменение шрифта происходит до печати просмотреть содержимое.  
  
##  <a name="a-namesettabstopsa--ceditviewsettabstops"></a><a name="settabstops"></a>CEditView::SetTabStops  
 Эта функция вызывается для определения позиций табуляции, используемый для отображения и печати.  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>Параметры  
 `nTabStops`  
 Ширина каждой позиции табуляции, в единицах диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Поддерживается только один ширину табуляции. ( `CEdit` объекты поддерживают несколько ширину переходов.) Ширина, в единицах диалогового окна, которое равно одной четвертой Средняя ширина символа (с учетом прописных и строчных букв только) шрифта, используемого во время печати или отображения. Не следует использовать `CEdit::SetTabStops` из-за `CEditView` необходимо кэшировать значение табуляции.  
  
 Эта функция изменяет только вкладки объекта, для которого он вызван. Чтобы изменить на вкладке позиции табуляции для каждого `CEditView` в приложении, следует вызвать каждый объект `SetTabStops` функции.  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода задает позиции табуляции в элементе управления для каждого четвертый символ тщательно Измеряя шрифт, который используется в элементе управления.  
  
 [!code-cpp[NVC_MFCDocView&#67;](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="a-nameunlockbuffera--ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>CEditView::UnlockBuffer  
 Вызовите эту функцию-член разблокировать буфер.  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Вызов `UnlockBuffer` после завершения использования указатель, возвращенный [LockBuffer](#lockbuffer).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC SUPERPAD](../../visual-cpp-samples.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Класс CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView-класс](../../mfc/reference/cricheditview-class.md)

