---
title: "CPropertySheet-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, tabs
- CPropertySheet class
- property sheets, CPropertySheet class
- tab dialog boxes
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
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
ms.openlocfilehash: 41ad7b598016b1fa04aa7ca63575f853195b5359
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertysheet-class"></a>CPropertySheet-класс
Представляет страницы свойств, также известные как диалоговые окна вкладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPropertySheet : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Создает объект `CPropertySheet`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertySheet::AddPage](#addpage)|Добавляет страницу в таблицу свойств.|  
|[CPropertySheet::Construct](#construct)|Создает объект `CPropertySheet`.|  
|[CPropertySheet::Create](#create)|Отображает страницу вкладки свойств.|  
|[CPropertySheet::DoModal](#domodal)|Отображает модальную страницу свойств.|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Указывает, использует ли окно свойств с накоплением или прокрутки вкладок.|  
|[CPropertySheet::EndDialog](#enddialog)|Завершает окно свойств.|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Извлекает индекс активной страницы свойств.|  
|[CPropertySheet::GetActivePage](#getactivepage)|Возвращает объект активной страницы.|  
|[CPropertySheet::GetPage](#getpage)|Извлекает указатель на указанную страницу.|  
|[CPropertySheet::GetPageCount](#getpagecount)|Возвращает количество страниц в окне свойств.|  
|[CPropertySheet::GetPageIndex](#getpageindex)|Извлекает индекс указанной страницы свойств.|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|Извлекает указатель на элемент управления вкладками.|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Преобразует единицы диалогового прямоугольника экрана единиц.|  
|[CPropertySheet::OnInitDialog](#oninitdialog)|Переопределите для ускорения инициализации листа свойств.|  
|[CPropertySheet::PressButton](#pressbutton)|Имитирует Выбор указанную кнопку в окне свойств.|  
|[CPropertySheet::RemovePage](#removepage)|Удаляет страницу из страницы свойств.|  
|[CPropertySheet::SetActivePage](#setactivepage)|Программно задает объект активной страницы.|  
|[CPropertySheet::SetFinishText](#setfinishtext)|Задает текст для кнопки "Готово".|  
|[CPropertySheet::SetTitle](#settitle)|Задает заголовок страницы свойств.|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Включает кнопки мастера.|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|Включает режим мастера.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) структуры. Предоставляет доступ к параметрам страницу основных свойств.|  
  
## <a name="remarks"></a>Примечания  
 Окно свойств состоит из `CPropertySheet` объектов и один или несколько [CPropertyPage](../../mfc/reference/cpropertypage-class.md) объектов. Платформа framework отображается в виде окна с набором индексов вкладки и области, которая содержит текущую страницу свойств. Когда пользователь переходит на определенную страницу, используя соответствующую вкладку.  
  
 `CPropertySheet`предоставляет поддержку для развернутого [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) структура введена в [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] и Windows NT 2000. Эта структура содержит дополнительные флаги и члены, которые поддерживают использование растрового фона «водяной знак».  
  
 Для отображения этих новых образов автоматически в ваш объект страницы свойств, передайте допустимые значения для точечного рисунка и палитру изображений в вызове [CPropertySheet::Construct](#construct) или [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Несмотря на то что `CPropertySheet` не является производным от [CDialog](../../mfc/reference/cdialog-class.md), управление `CPropertySheet` объекта — как управление `CDialog` объекта. Например, для создания свойств требуется создание двух частей: вызов конструктора, а затем вызвать [DoModal](#domodal) для модальных свойств или [создать](#create) для страницы вкладки свойств. `CPropertySheet`Существует два вида конструкторов: [CPropertySheet::Construct](#construct) и [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 При построении `CPropertySheet` объекта, некоторые [стили окна](../../mfc/reference/window-styles.md) может привести к возникновению исключения первого шанса. Это происходит из системы, попытка изменить стиль страницы свойств перед созданием листа. Чтобы избежать этого исключения, убедитесь, что при создании задавать следующие стили вашего `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Следующие стили являются необязательными и не вызовет исключения первого шанса:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Любой другой `Window Styles` запрещены должна быть включена.  
  
 Обмен данными между `CPropertySheet` объекта и внешнего объекта похож на обмен данными с `CDialog` объекта. Важное отличие заключается в параметры свойств обычно являются переменные-члены `CPropertyPage` объектов, а не из `CPropertySheet` сам объект.  
  
 Можно создать тип вкладка диалогового окна вызывается мастер, который состоит из свойств последовательностью страницы свойств, которые проводят пользователя через последовательность шагов операции, такие как настройки устройства или создание информационного бюллетеня. В диалоговом окне вкладку тип мастера страницы свойств нет вкладки и только одно свойство страница видна одновременно. Кроме того, вместо **ОК** и **Apply Now** имеет диалоговое окно вкладки тип мастера кнопок, **обратно** кнопки, **Далее** или **Готово** кнопки, **отменить** кнопки и **помочь** кнопки.  
  
 Чтобы создать диалоговое окно мастера, выполните те же действия, необходимые для создания стандартных свойств, но вызывает [SetWizardMode](#setwizardmode) перед вызовом метода [DoModal](#domodal). Чтобы включить кнопки с помощью мастера, вызовите [SetWizardButtons](#setwizardbuttons), настройка их функции и внешний вид с помощью флагов. Чтобы включить **Готово** кнопку, вызовите метод [SetFinishText](#setfinishtext) после выполнения действия пользователя на последней странице мастера.  
  
 Дополнительные сведения об использовании `CPropertySheet` объектов, см. в статье [вкладки свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md). Кроме того, в статье базы знаний Q146916: Практическое руководство: создание CPropertySheet немодальных с помощью стандартных кнопок, а статья Q300606: руководство: разработка свойств в MFC.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="addpage"></a>CPropertySheet::AddPage  
 Добавляет предоставленный страницы с вкладкой «справа» в окне свойств.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 `pPage`  
 Указывает на страницу, чтобы добавить к странице свойств. Не может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Добавление страниц свойств в порядке слева направо, они должны отображаться.  
  
 `AddPage`Добавляет [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) объект `CPropertySheet` объект в список страниц, но не на самом деле создает окно страницы. Платформа откладывает Создание окна для страницы, пока пользователь выбирает эту страницу.  
  
 При добавлении страницы свойств с помощью `AddPage`, `CPropertySheet` является родительским для `CPropertyPage`. Чтобы получить доступ к странице свойств на странице свойств, вызовите [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).  
  
 Нет необходимости ждать до создания окно свойство `AddPage`. Как правило, будет вызывать `AddPage` перед вызовом метода [DoModal](#domodal) или [создать](#create).  
  
 При вызове метода `AddPage` после отображения страницы свойств, строке вкладок будет отражать новые страницы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#129;](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="construct"></a>CPropertySheet::Construct  
 Создает объект `CPropertySheet`.  
  
```  
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDCaption`  
 Идентификатор заголовок, используемый для страницы свойств.  
  
 `pParentWnd`  
 Указатель на родительское окно свойств. Если **NULL**, родительского окна будут главного окна приложения.  
  
 `iSelectPage`  
 Индекс страницы, которая изначально будет находиться в начале списка. По умолчанию используется первая страница добавлена в лист.  
  
 `pszCaption`  
 Указатель на строку, содержащую текст, который используется для страницы свойств. Не может быть **NULL**.  
  
 `hbmWatermark`  
 Дескриптор точечного рисунка водяного знака страницы свойств.  
  
 `hpalWatermark`  
 Дескриптор палитры растрового изображения водяного знака и заголовка точечного рисунка.  
  
 `hbmHeader`  
 Дескриптор точечного рисунка заголовок страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, если один из конструкторов класса уже не был вызван. Например, можно вызвать `Construct` при объявлении или выделить массивы из `CPropertySheet` объектов. В случае с массивами, необходимо вызвать метод `Construct` для каждого элемента в массиве.  
  
 Чтобы открыть окно свойств, вызовите [DoModal](#domodal) или [создать](#create). Строка, содержащаяся в качестве первого параметра будут помещены в строке заголовка для страницы свойств.  
  
 Можно отобразить изображения водяного знака и заголовка автоматически при использовании прототипов третьего или четвертого `Construct`, перечисленных выше, и передайте допустимые значения для `hbmWatermark`, `hpalWatermark`, или `hbmHeader` параметры.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, в каких обстоятельствах можно вызвать `Construct`.  
  
 [!code-cpp[NVC_MFCDocView&#130;](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="cpropertysheet"></a>CPropertySheet::CPropertySheet  
 Создает объект `CPropertySheet`.  
  
```  
CPropertySheet();

 
explicit CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
explicit CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDCaption`  
 Идентификатор заголовок, используемый для страницы свойств.  
  
 `pParentWnd`  
 Указывает для родительского окна окно свойств. Если **NULL**, родительского окна будут главного окна приложения.  
  
 `iSelectPage`  
 Индекс страницы, которая изначально будет находиться в начале списка. По умолчанию используется первая страница добавлена в лист.  
  
 `pszCaption`  
 Указывает строку, содержащую текст, который используется для страницы свойств. Не может быть **NULL**.  
  
 `hbmWatermark`  
 Дескриптор точечного рисунка фона страницы свойств.  
  
 `hpalWatermark`  
 Дескриптор палитры растрового изображения водяного знака и заголовка точечного рисунка.  
  
 `hbmHeader`  
 Дескриптор точечного рисунка заголовок страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть окно свойств, вызовите [DoModal](#domodal) или [создать](#create). Строка, содержащаяся в качестве первого параметра будут помещены в строке заголовка для страницы свойств.  
  
 Если у вас есть несколько параметров (например, если вы используете массив), используйте [создания](#construct) вместо `CPropertySheet`.  
  
 Можно отобразить изображения водяного знака и заголовка автоматически при использовании прототипов третьего или четвертого `CPropertySheet`, см. выше, и передайте допустимые значения для `hbmWatermark`, `hpalWatermark`, или `hbmHeader` параметры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#131;](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="create"></a>CPropertySheet::Create  
 Отображает страницу вкладки свойств.  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)–1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно. Если **NULL**, родителем является рабочий стол.  
  
 `dwStyle`  
 Стили окна для страницы свойств. Полный список доступных стилей см. в разделе [стили окна](../../mfc/reference/window-styles.md).  
  
 `dwExStyle`  
 Расширенные стили окна для страницы свойств. Полный список доступных стилей см. в разделе [расширенные стили окна](../../mfc/reference/extended-window-styles.md)  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств создано успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов **создать** может быть внутри конструктора или его можно вызвать после вызова конструктора.  
  
 Стиль по умолчанию, выраженное, передав -1 как `dwStyle`, на самом деле **WS_SYSMENU |** `WS_POPUP`**| WS_CAPTION | DS_MODALFRAME | DS_CONTEXTHELP | WS_VISIBLE**. Значение по умолчанию расширенный стиль окна, выраженное, передав 0 как `dwExStyle`, на самом деле **WS_EX_DLGMODALFRAME**.  
  
 **Создать** функция-член возвращает сразу после создания страницы свойств. Чтобы уничтожить окно свойств, вызовите [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).  
  
 Безрежимные свойств отображаются с помощью вызова **создать** нет кнопки OK, Отмена, применить и справки как модальное свойств. Необходимо создать нужные кнопки пользователем.  
  
 Для отображения модальных свойств, вызовите [DoModal](#domodal) вместо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#132;](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#133;](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="domodal"></a>CPropertySheet::DoModal  
 Отображает модальную страницу свойств.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IDOK`или `IDCANCEL` Если функция была успешно; в противном случае 0 или -1. Установлен ли окно свойств как мастера (см. [SetWizardMode](#setwizardmode)), `DoModal` возвращает либо `ID_WIZFINISH` или `IDCANCEL`.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение соответствует идентификатору, закрыть окно свойств элемента управления. После возврата этой функции windows, соответствующее окно свойств и все страницы будут был уничтожен. Сами объекты продолжают существовать. Как правило, вы получите данные из [CPropertyPage](../../mfc/reference/cpropertypage-class.md) объектов после `DoModal` возвращает `IDOK`.  
  
 Для отображения немодальных свойств, вызовите [создать](#create) вместо.  
  
 При создании страницы свойств из соответствующего ресурса диалогового окна может привести к первичной обработки исключений. Это происходит из страницы свойств, изменив стиль ресурса диалогового окна необходимые стиля, до создания страницы. Из-за ресурсов доступны только для чтения, это приведет к исключению. Система обрабатывает исключение и делает копию измененных ресурсов. Исключения первого шанса может игнорироваться.  
  
> [!NOTE]
>  Это исключение должно обрабатываться операционной системы при компиляции с помощью модели асинхронной обработки исключений. Дополнительные сведения о модели обработки исключений см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md). В этом случае не заключайте вызовы `CPropertySheet::DoModal` с блоком try-catch C++ в которой catch обрабатывает все исключения, например, `catch (...)`. Этот блок будет обрабатывать предназначены для операционной системы и непредсказуемым причину исключения. Тем не менее можно безопасно использовать обработка исключений C++ и определенных типов исключений или структурированная обработка исключений где передать исключение нарушения прав доступа к операционной системе.  
  
 Чтобы избежать возникновения этого исключения первого шанса, вручную гарантировать наличие правильного окно свойств [стили окна](../../mfc/reference/window-styles.md). Необходимо задать следующие стили для окна свойств:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Можно использовать следующие необязательные стили без возникновения исключения первого шанса.  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Отключите все другие стили Windows, так как они не совместимы со страницами свойств. Этот совет не относится к расширенные стили. Задание этих стандартных стилей соответствующим образом гарантирует, что окно свойств не должен изменяться и позволит избежать создания исключения первого шанса.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::AddPage](#addpage).  
  
##  <a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs  
 Указывает, следует ли стека строки вкладок в окне свойств.  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>Параметры  
 `bStacked`  
 Указывает, включены ли с накоплением вкладки в окне свойств. Отключить, задав с накоплением строк теги `bStacked` для **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию Если окно свойств содержит дополнительные вкладки, чем может поместиться в одну строку в ширину страницы свойств вкладки складываются в несколько строк. Для использования прокрутки вкладок вместо вкладки наложения, вызовите `EnableStackedTabs` с `bStacked` значение **FALSE** перед вызовом метода [DoModal](#domodal) или [создать](#create).  
  
 Необходимо вызвать метод `EnableStackedTabs` при создании модального или немодального свойств. Для включения этого стиля в `CPropertySheet`-производный класс, написать обработчик сообщений для `WM_CREATE`. В переопределенной версии [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), вызовите **EnableStackedTabs (FALSE)** до вызова реализации базового класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#134;](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="enddialog"></a>CPropertySheet::EndDialog  
 Завершает окно свойств.  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>Параметры  
 *nEndID*  
 Идентификатор для использования в качестве возвращаемого значения свойств.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается инфраструктурой при нажатии ОК, отмены или кнопку Закрыть. Вызов этой функции-члена, если происходит событие, которое следует закрыть окно свойств.  
  
 Эта функция-член используется только с помощью модального диалогового окна.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::PressButton](#pressbutton).  
  
##  <a name="getactiveindex"></a>CPropertySheet::GetActiveIndex  
 Возвращает номер индекса окно свойств активной страницы, а затем использует возвращенный номер индекса как параметр `GetPage`.  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер индекса активной страницы.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="getactivepage"></a>CPropertySheet::GetActivePage  
 Извлекает окно свойств активной страницы.  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущей странице.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член для выполнения некоторых операций на текущей странице.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#135;](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>CPropertySheet::GetPage  
 Возвращает указатель на указанную страницу на этой странице свойств.  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPage`  
 Индекс требуемой страницы, начиная с 0. Должно быть между 0 и меньше, чем количество страниц в окне свойств, включительно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на страницы, соответствующий `nPage` параметр.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpagecount"></a>CPropertySheet::GetPageCount  
 Определяет число страниц в настоящее время в окне свойств.  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество страниц в окне свойств.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpageindex"></a>CPropertySheet::GetPageIndex  
 Извлекает индекс указанной страницы в окне свойств.  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 `pPage`  
 Указывает на страницу с индексом, который требуется найти. Не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер индекса страницы.  
  
### <a name="remarks"></a>Примечания  
 Например, можно использовать `GetPageIndex` для получения индекса страницы, чтобы использовать [SetActivePage](#setactivepage) или [GetPage](#getpage).  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="gettabcontrol"></a>CPropertySheet::GetTabControl  
 Извлекает указатель на набор вкладок, для чего-то конкретного элементу управления tab (то есть для использования этих интерфейсов API в [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент управления вкладками.  
  
### <a name="remarks"></a>Примечания  
 Например можно Вызовите эту функцию-член, если вы хотите добавить точечных рисунков для каждой из вкладок во время инициализации.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#136;](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>CPropertySheet::m_psh  
 Структуры, члены которого хранения характеристики [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  
  
### <a name="remarks"></a>Примечания  
 Использовать эту структуру для инициализации внешний вид страницы свойств после его создания, но перед отображением с [DoModal](#domodal) функции-члена. Например, задать `dwSize` членом `m_psh` размер необходимо иметь свойств.  
  
 Дополнительные сведения об этой структуры, включая список ее членов в разделе **PROPSHEETHEADER** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#143;](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>CPropertySheet::MapDialogRect  
 Преобразует единицы диалогового прямоугольника экрана единиц.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указывает [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий диалоговым окном координаты для преобразования.  
  
### <a name="remarks"></a>Примечания  
 С точки зрения текущего диалогового базовой единицей производными от среднюю ширину и высоту символов шрифта для текста диалоговое указаны единиц диалоговых окон. Одна единица — одну четверть ширины базы единицы диалогового, а одна единица — одну восьмую высота основы единицы диалогового.  
  
 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows функция возвращает сведения о размере шрифта системы, но можно указать другой шрифт для каждой страницы свойств, если используется **DS_SETFONT** стиль в файле определения ресурсов. [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) функции Windows, описанных в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], использует соответствующий шрифт для текущего окна.  
  
 `MapDialogRect` Функция-член заменяет единицы диалоговых окон в `lpRect` с экрана устройства (в пикселях), чтобы прямоугольник можно использовать для создания диалогового окна или разместить элемент управления в поле.  
  
##  <a name="oninitdialog"></a>CPropertySheet::OnInitDialog  
 Переопределения для дополнения инициализации листа свойств.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Включение приложения фокус ввода для элемента управления в окне свойств. Если **OnInitDialog** возвращает ненулевое значение, Windows устанавливает фокус ввода на первый элемент управления в окне свойств. Приложение может возвращают 0 только в том случае, если он явно установлен фокус ввода для элемента управления в окне свойств.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается в ответ на **WM_INITDIALOG** сообщение. Это сообщение отправляется в окно свойств во время [создать](#create) или [DoModal](#domodal) вызовы, которые происходят непосредственно перед выводом страницы свойств.  
  
 Переопределите эту функцию-член, если требуется выполнять специальную обработку при инициализации страницы свойств. Переопределенные версии сначала вызвать базовый класс `OnInitDialog` , но не принимать во внимание возвращаемого значения. Обычно будет возвращать **TRUE** из переопределяемого члена функции.  
  
 Не требуется запись сопоставления сообщений для этой функции-члена.  
  
##  <a name="pressbutton"></a>CPropertySheet::PressButton  
 Имитирует Выбор указанную кнопку в окне свойств.  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>Параметры  
 `nButton`  
 nButton: Определяет нажатие кнопки. Этот параметр может принимать одно из следующих значений:  
  
- **PSBTN_BACK** нажимает кнопку "Назад".  
  
- **PSBTN_NEXT** нажимает кнопку Далее.  
  
- **PSBTN_FINISH** нажимает кнопку Готово.  
  
- **PSBTN_OK** нажимает кнопку «OK».  
  
- **PSBTN_APPLYNOW** нажимает кнопку Применить.  
  
- **PSBTN_CANCEL** нажимает кнопку "Отмена".  
  
- **PSBTN_HELP** нажимает кнопку справки.  
  
### <a name="remarks"></a>Примечания  
 В разделе [PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) Дополнительные сведения о сообщении Windows SDK Pressbutton.  
  
 Вызов `PressButton` не будет отправлять [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) уведомления через страницу свойств для платформы. Чтобы посылать уведомления, вызовите [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#137;](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>CPropertySheet::RemovePage  
 Удаляет страницу из страницы свойств, а также уничтожает соответствующее окно.  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 `pPage`  
 Указывает на страницу, чтобы удалить из страницы свойств. Не может быть `NULL`.  
  
 `nPage`  
 Индекс страницы должны быть удалены. Должно быть между 0 и меньше, чем количество страниц в окне свойств, включительно.  
  
### <a name="remarks"></a>Примечания  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md) сам объект не уничтожается, пока владелец `CPropertySheet` закрытия окна.  
  
##  <a name="setactivepage"></a>CPropertySheet::SetActivePage  
 Изменение активной страницы.  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 `nPage`  
 Индекс страницы для задания. Его должно быть между 0 и меньше, чем количество страниц в окне свойств, включительно.  
  
 `pPage`  
 Указывает на страницу, чтобы задать в окне свойств. Он не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств активирован успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Например, используйте `SetActivePage` , если действие пользователя на одной странице должно приводить к другим страница станет активной страницы.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="setfinishtext"></a>CPropertySheet::SetFinishText  
 Задает текст кнопки Готово команды.  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указывает текст, отображаемый на команду "Готово".  
  
### <a name="remarks"></a>Примечания  
 Вызов `SetFinishText` для отображения текста кнопки Готово и скрыть кнопки Далее и назад, после завершения пользователем действия на последней странице мастера.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="settitle"></a>CPropertySheet::SetTitle  
 Указывает заголовок страницы свойств (текст, отображаемый в строке заголовка окна фрейма).  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nStyle`  
 Задает стиль заголовка листа свойств. Необходимо указать стиль на 0 или как **PSH_PROPTITLE**. Если стиль имеет значение **PSH_PROPTITLE**, отображается слово «Свойства» после текста, указанного в качестве заголовка. Например, вызов `SetTitle`(«Простой», **PSH_PROPTITLE**) приведет к заголовок листа свойство «Простых свойств».  
  
 `lpszText`  
 Указывает текст, который используется в качестве названия в заголовке окна свойств.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию свойств используется параметр заголовка в конструктор листа свойств.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#139;](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons  
 Включает или отключает кнопку "Назад", "Next" или "Готово" в окне свойств мастера.  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Набор флагов, настраивать функции и внешний вид кнопок мастера. Этот параметр может быть сочетанием следующих значений:  
  
- **PSWIZB_BACK** кнопку «Назад»  
  
- **PSWIZB_NEXT** кнопку Далее  
  
- **PSWIZB_FINISH** кнопки "Готово"  
  
- **PSWIZB_DISABLEDFINISH** кнопки Готово отключено  
  
### <a name="remarks"></a>Примечания  
 Вызов `SetWizardButtons` только в том случае, когда открыта диалогового окна; невозможно вызвать `SetWizardButtons` перед вызовом метода [DoModal](#domodal). Как правило, следует вызывать `SetWizardButtons` из [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).  
  
 Если обратно после кнопок пользователя и вы хотите изменить текст на "Готово" или скрыть следующего завершения мастера, вызов [SetFinishText](#setfinishtext). Обратите внимание, что совместно ту же кнопку Готово и далее. Можно отобразить окончания или кнопку Далее за один раз, но не оба.  
  
### <a name="example"></a>Пример  
 Объект `CPropertySheet` содержит три страницы свойств мастера: `CStylePage`, `CColorPage`, и `CShapePage`.  В следующем фрагменте кода показано, как включить и отключить **обратно** и **Далее** кнопки на странице мастера.  
  
 [!code-cpp[NVC_MFCDocView&#140;](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#141;](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>CPropertySheet::SetWizardMode  
 Устанавливает страницу свойств как мастера.  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Примечания  
 Страница свойств мастера основной характеристикой является пользователь переходит с помощью Далее или Готово, обратно что кнопки вместо вкладки отмены.  
  
 Вызов `SetWizardMode` перед вызовом метода [DoModal](#domodal). После вызова метода `SetWizardMode`, `DoModal` будет возвращать либо **ID_WIZFINISH** (если пользователь закрывает с кнопки «Готово») или **IDCANCEL**.  
  
 `SetWizardMode`Устанавливает флаг PSH_WIZARD.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#142;](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Пример MFC SNAPVW](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




