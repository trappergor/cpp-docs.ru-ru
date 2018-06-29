---
title: CPropertySheet-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f194b8119cb080c9a3b29e63781595ada0027ef
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079777"
---
# <a name="cpropertysheet-class"></a>CPropertySheet-класс
Представляет страницы свойств, также известные как диалоговые окна вкладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPropertySheet : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Создает объект `CPropertySheet`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPropertySheet::AddPage](#addpage)|Добавляет страницу в таблицу свойств.|  
|[CPropertySheet::Construct](#construct)|Создает объект `CPropertySheet`.|  
|[CPropertySheet::Create](#create)|Отображает немодальный лист свойств.|  
|[CPropertySheet::DoModal](#domodal)|Отображает модальную страницу свойств.|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Указывает, использует ли окно свойств с накоплением или прокрутки вкладок.|  
|[CPropertySheet::EndDialog](#enddialog)|Завершает окно свойств.|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Возвращает индекс активной страницы свойств.|  
|[CPropertySheet::GetActivePage](#getactivepage)|Возвращает объект активной странице.|  
|[CPropertySheet::GetPage](#getpage)|Извлекает указатель на указанной странице.|  
|[CPropertySheet::GetPageCount](#getpagecount)|Возвращает число страниц в окне свойств.|  
|[CPropertySheet::GetPageIndex](#getpageindex)|Извлекает индекс заданного страницы свойств.|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|Извлекает указатель на элемент управления вкладки.|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Преобразует единицы диалогового окна прямоугольника с экрана устройства.|  
|[CPropertySheet::OnInitDialog](#oninitdialog)|Переопределите для ускорения инициализации листа свойств.|  
|[CPropertySheet::PressButton](#pressbutton)|Имитирует Выбор указанной кнопки в окне свойств.|  
|[CPropertySheet::RemovePage](#removepage)|Удаляет страницу из страницы свойств.|  
|[CPropertySheet::SetActivePage](#setactivepage)|Программным образом задается объект активной странице.|  
|[CPropertySheet::SetFinishText](#setfinishtext)|Задает текст для кнопки "Готово".|  
|[CPropertySheet::SetTitle](#settitle)|Задает заголовок страницы свойств.|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Позволяет кнопок мастера.|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|Включает режим мастера.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) структуры. Предоставляет доступ к параметрам основных свойств листа.|  
  
## <a name="remarks"></a>Примечания  
 Страница свойств состоит из `CPropertySheet` объекта и один или несколько [CPropertyPage](../../mfc/reference/cpropertypage-class.md) объектов. Платформа отображает страницу свойств в окне с набором вкладку индексов и область, которая содержит текущую страницу. Пользователь переходит на определенную страницу, используя соответствующую вкладку.  
  
 `CPropertySheet` обеспечивает поддержку развернутом [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) структура введена в [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] и Windows NT 2000. Эта структура содержит дополнительные флаги и члены, которые поддерживают использование «водяного знака» фоновый рисунок.  
  
 Для отображения этих новых образов автоматически в ваш объект вкладки свойств, передайте допустимые значения для точечного рисунка и палитру изображений в вызове [CPropertySheet::Construct](#construct) или [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Несмотря на то что `CPropertySheet` не является производным от [CDialog](../../mfc/reference/cdialog-class.md), управление `CPropertySheet` объект аналогичен управление `CDialog` объекта. Например, для создания вкладки свойств требуется создание двух частей: вызов конструктора, а затем вызвать [DoModal](#domodal) для модальную страницу свойств или [создать](#create) для немодальный лист свойств. `CPropertySheet` Существует два типа конструкторов: [CPropertySheet::Construct](#construct) и [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 При построении `CPropertySheet` объект, некоторые [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) может привести к возникновению исключения первого шанса. Это результаты из системы, попытка изменить стиль свойств перед созданием листа. Чтобы избежать этого исключения, убедитесь, что при создании заданы следующие стили вашего `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Следующие стили являются необязательными и не вызовет исключения первого шанса:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Любой другой `Window Styles` запрещены и их не следует включить.  
  
 Обмен данными между `CPropertySheet` объекта и внешнего объекта аналогично обмен данными с `CDialog` объекта. Важное отличие заключается в параметрах вкладки свойств обычно являются переменные-члены `CPropertyPage` объектов, а не из `CPropertySheet` сам объект.  
  
 Можно создать тип вкладка диалогового окна вызван мастер, который состоит из окна свойств последовательностью страницы свойств, которые проводят пользователя через шаги операции, такие как Настройка устройства или создание информационный бюллетень. В диалоговом окне вкладку тип мастера страницы свойств не имеют вкладок и только одно свойство страница видна одновременно. Кроме того, вместо того, **ОК** и **применить** содержит кнопки, диалоговое окно вкладки тип мастера **обратно** кнопки, **Далее** или  **Готово** кнопки, **отменить** кнопки и **справки** кнопки.  
  
 Чтобы создать диалоговое окно мастера, выполните те же действия, которые необходимо использовать для создания стандартных свойств, но вызывает [SetWizardMode](#setwizardmode) перед вызовом метода [DoModal](#domodal). Чтобы включить кнопок мастера, вызовите [SetWizardButtons](#setwizardbuttons), с помощью флагов, чтобы настраивать их внешний вид и функции. Чтобы включить **Готово** кнопку, вызовите метод [SetFinishText](#setfinishtext) после выполнения действия пользователя на последней странице мастера.  
  
 Дополнительные сведения об использовании `CPropertySheet` объектов, см. в статье [вкладки свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md). Кроме того, в статье базы знаний Q146916: Практическое руководство: создание CPropertySheet немодальный с стандартные кнопки, а статья Q300606: Практическое руководство: проектировать страницу свойств с раскрывающимися списками MFC.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="addpage"></a>  CPropertySheet::AddPage  
 Добавляет предоставленный страницы с вкладкой «справа» в окне свойств.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 *Физ_страница*  
 Указывает на страницу, чтобы добавить в таблицу свойств. Не может быть **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Добавление страниц свойств в порядке слева направо, который будет отображаться.  
  
 `AddPage` Добавляет [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) объект `CPropertySheet` объект в список страниц, но фактически не создает окно страницы. Платформа откладывает Создание окна для страницы, пока пользователь выбирает эту страницу.  
  
 При добавлении страницы свойств с помощью `AddPage`, `CPropertySheet` является родительским для `CPropertyPage`. Чтобы получить доступ к странице свойств на странице свойств, вызовите [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).  
  
 Нет необходимости ждать Создание окно страницы свойств для вызова `AddPage`. Как правило, вы будете вызывать `AddPage` перед вызовом [DoModal](#domodal) или [создать](#create).  
  
 При вызове метода `AddPage` после отображения страницы свойств, строке вкладок будут отражать новые страницы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="construct"></a>  CPropertySheet::Construct  
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
 *nIDCaption*  
 Идентификатор заголовка для страницы свойств.  
  
 *pParentWnd*  
 Указатель на родительское окно страницы свойств. Если **NULL**, родительское окно будет главного окна приложения.  
  
 *iSelectPage*  
 Индекс страницы, которая изначально будет находиться в начале списка. По умолчанию — это первая страница, добавлен в лист.  
  
 *pszCaption*  
 Указатель на строку, содержащую текст, который используется для страницы свойств. Не может быть **NULL**.  
  
 *hbmWatermark*  
 Дескриптор растрового изображения водяного знака страницы свойств.  
  
 *hpalWatermark*  
 Дескриптор палитры растрового изображения водяного знака и/или заголовок растрового изображения.  
  
 *hbmHeader*  
 Дескриптор точечного рисунка заголовок страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, если один из конструкторов класса уже не был вызван. Например, вызов `Construct` при объявлении или выделить массивы из `CPropertySheet` объектов. В случае массивов, необходимо вызвать метод `Construct` для каждого элемента в массиве.  
  
 Чтобы открыть окно свойств, вызовите [DoModal](#domodal) или [создать](#create). Строка, содержащаяся в качестве первого параметра будут помещены в строке заголовка для страницы свойств.  
  
 Можно отобразить изображения водяного знака и/или заголовка автоматически при использовании прототипов третий и четвертый `Construct`, перечисленных выше, и передать допустимые значения для *hbmWatermark*, *hpalWatermark* , и/или *hbmHeader* параметров.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, в каких обстоятельствах Вы вызовет `Construct`.  
  
 [!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="cpropertysheet"></a>  CPropertySheet::CPropertySheet  
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
 *nIDCaption*  
 Идентификатор заголовка для страницы свойств.  
  
 *pParentWnd*  
 Указывает на родительское окно страницы свойств. Если **NULL**, родительское окно будет главного окна приложения.  
  
 *iSelectPage*  
 Индекс страницы, которая изначально будет находиться в начале списка. По умолчанию — это первая страница, добавлен в лист.  
  
 *pszCaption*  
 Указывает строку, содержащую текст, который используется для страницы свойств. Не может быть **NULL**.  
  
 *hbmWatermark*  
 Дескриптор в качестве фонового изображения страницы свойств.  
  
 *hpalWatermark*  
 Дескриптор палитры растрового изображения водяного знака и/или заголовок растрового изображения.  
  
 *hbmHeader*  
 Дескриптор к растровому изображению заголовка страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть окно свойств, вызовите [DoModal](#domodal) или [создать](#create). Строка, содержащаяся в качестве первого параметра будут помещены в строке заголовка для страницы свойств.  
  
 Если имеется несколько параметров (например, если вы используете массив), используйте [создания](#construct) вместо `CPropertySheet`.  
  
 Можно отобразить изображения водяного знака и/или заголовка автоматически при использовании прототипов третий и четвертый `CPropertySheet`выше, и передайте допустимые значения для *hbmWatermark*, *hpalWatermark*, и / или *hbmHeader* параметров.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="create"></a>  CPropertySheet::Create  
 Отображает немодальный лист свойств.  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>Параметры  
 *pParentWnd*  
 Указатель на родительское окно. Если **NULL**, родительским является рабочий стол.  
  
 *dwStyle*  
 Стили окна для страницы свойств. Полный список доступных стилей см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 *dwExStyle*  
 Расширенные стили окна для страницы свойств. Полный список доступных стилей см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов `Create` может быть внутри конструктора, или ее можно вызывать после вызова конструктора.  
  
 Стиль по умолчанию, выраженное путем передачи -1, поскольку *dwStyle*, на самом деле **WS_SYSMENU&#124;**`WS_POPUP`**&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_ CONTEXTHELP&#124;WS_VISIBLE**. Значение по умолчанию расширенный стиль окна, выраженное путем передачи 0 как *dwExStyle*, на самом деле **WS_EX_DLGMODALFRAME**.  
  
 `Create` Функция-член возвращает сразу после создания страницы свойств. Чтобы окончательно удалить окно свойств, вызовите [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).  
  
 Вкладки свойств без режима отображения с помощью вызова `Create` нет кнопки ОК, "Отмена", применить и справки, как модальные свойств. Требуемый кнопки должны создаваться пользователем.  
  
 Чтобы отобразить модальную страницу свойств, вызовите [DoModal](#domodal) вместо него.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="domodal"></a>  CPropertySheet::DoModal  
 Отображает модальную страницу свойств.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IDOK` или `IDCANCEL` Если функция была успешно; в противном случае значение 0 или -1. Если окно свойств было установлено как мастер (в разделе [SetWizardMode](#setwizardmode)), `DoModal` возвращает либо `ID_WIZFINISH` или `IDCANCEL`.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение соответствует идентификатору элемента управления, закрыто окно свойств. После возврата этой функции windows, соответствующее окно свойств и все страницы будут уничтожены. Сами объекты по-прежнему будет существовать. Как правило, будут получены данные от [CPropertyPage](../../mfc/reference/cpropertypage-class.md) объектов после `DoModal` возвращает `IDOK`.  
  
 Чтобы отобразить немодальный лист свойств, вызовите [создать](#create) вместо него.  
  
 При создании страницы свойств из его соответствующий ресурс диалогового окна может привести к первичном исключении. Это результаты из страницы свойств, изменение стиля ресурса диалогового окна необходимые стиль перед созданием страницы. Так как ресурсы доступны только для чтения, это приводит к возникновению исключения. Система обрабатывает исключение и создает копию измененных ресурсов. Исключения первого шанса может игнорироваться.  
  
> [!NOTE]
>  Это исключение должно обрабатываться операционной системой при компиляции с помощью модели асинхронной обработки исключений. Дополнительные сведения о модели обработки исключений см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md). В этом случае не создают оболочки для вызовов `CPropertySheet::DoModal` с помощью блока try-catch-C++ в которой catch обрабатывает все исключения, например, `catch (...)`. Этот блок будет обрабатывать исключение, предназначен для операционной системы и причина к непредсказуемому поведению. Тем не менее можно безопасно использовать обработка исключений C++ и исключения определенных типов или структурированная обработка исключений где нарушение прав доступа исключение передается через операционную систему.  
  
 Чтобы избежать возникновения этого исключения первого шанса, вручную гарантировать наличие правильного окно свойств [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). Необходимо задать следующие стили для страницы свойств:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Без исключения первого шанса, можно использовать следующие дополнительные стили:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Отключите все другие стили, Windows, так как они не совместимы со страницами свойств. Это требование не применяется к расширенные стили. Установка этих стандартных стилей соответствующим образом гарантирует, что окно свойств не должен изменяться и позволит избежать создания исключения первого шанса.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::AddPage](#addpage).  
  
##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs  
 Указывает, следует ли стека рядов вкладок в окне свойств.  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>Параметры  
 *bStacked*  
 Указывает, включены ли с накоплением вкладок в окне свойств. Отключить, задав с накоплением строк теги *bStacked* для **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию Если окно свойств содержит больше вкладок, чем может поместиться в одной строке на ширину страницы свойств вкладки складываются в несколько строк. Для прокрутки вкладки используются вместо расположения символов табуляции, вызовите `EnableStackedTabs` с *bStacked* значение **FALSE** перед вызовом [DoModal](#domodal) или [создать](#create).  
  
 Необходимо вызвать метод `EnableStackedTabs` при создании модального или немодальный лист свойств. Для включения в этот стиль `CPropertySheet`-производного класса, написать обработчик сообщений для WM_CREATE. В переопределенная версия [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), вызовите **EnableStackedTabs (FALSE)** до вызова реализации базового класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="enddialog"></a>  CPropertySheet::EndDialog  
 Завершает окно свойств.  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>Параметры  
 *nEndID*  
 Идентификатор для использования в качестве возвращаемого значения свойств.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой при нажатии ОК, "Отмена" или кнопку Закрыть. Вызовите эту функцию-член, если происходит событие, которое следует закрыть окно свойств.  
  
 Эта функция-член используется только с помощью модального диалогового окна.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::PressButton](#pressbutton).  
  
##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex  
 Возвращает индекс активной страницы окно свойств и затем использует возвращенный номер индекса в качестве параметра для `GetPage`.  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер индекса активной страницы.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage  
 Извлекает окно свойств активной странице.  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активной странице.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член для выполнения некоторых операций на активной странице.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>  CPropertySheet::GetPage  
 Возвращает указатель на указанную страницу в данной вкладкой свойств.  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nPage*  
 Индекс нужной странице, начиная с 0. Должен быть между 0 и меньше, чем количество страниц в окне свойств, включительно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на соответствующий для *nPage* параметра.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount  
 Определяет число страниц в настоящее время в окне свойств.  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество страниц в окне свойств.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex  
 Извлекает индекс указанной страницы в окне свойств.  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 *Физ_страница*  
 Указывает страницу с индексом, который требуется найти. Не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер индекса страницы.  
  
### <a name="remarks"></a>Примечания  
 Например, можно использовать `GetPageIndex` для получения индекса страницы, чтобы использовать [SetActivePage](#setactivepage) или [GetPage](#getpage).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl  
 Извлекает указатель на набор вкладок, сделать нечто, относящееся к элементу управления вкладки (то есть, для использования этих интерфейсов API в [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент управления вкладки.  
  
### <a name="remarks"></a>Примечания  
 Например можно Вызовите эту функцию-член, если вы хотите добавить каждой из вкладок растровые изображения во время инициализации.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>  CPropertySheet::m_psh  
 Структуры, члены которого хранения характеристики [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  
  
### <a name="remarks"></a>Примечания  
 Использовать эту структуру для инициализации внешний вид страницы свойств, после его создания, но перед отображением с [DoModal](#domodal) функции-члена. Например, задать *dwSize* членом `m_psh` размер чтобы свойств обязательно применение.  
  
 Дополнительные сведения об этой структуры, в том числе список его элементов. в разделе **PROPSHEETHEADER** в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect  
 Преобразует единицы диалогового окна прямоугольника с экрана устройства.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpRect*  
 Указывает на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий диалоговым окном координаты для преобразования.  
  
### <a name="remarks"></a>Примечания  
 С точки зрения текущего диалогового окна базовой единицей производными среднее ширину и высоту символов в шрифта для текста диалогового окна указаны единицы диалогового окна. Одна единица — четверти ширины базы единицы диалогового окна, а одна единица — одну восьмую высоты базовой единицы диалогового окна.  
  
 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows функция возвращает сведения о размере для системного шрифта, но можно указать другой шрифт для каждой страницы свойств, если вы используете **DS_SETFONT** стиля в файл определения ресурсов. [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) Windows, описанных в Windows SDK, использует соответствующий шрифт этого диалогового окна.  
  
 `MapDialogRect` Функция-член заменяет единицы диалогового окна в *lpRect* с экрана устройства (в пикселях), чтобы прямоугольник можно использовать для создания диалогового окна или разместить элемент управления в поле.  
  
##  <a name="oninitdialog"></a>  CPropertySheet::OnInitDialog  
 Переопределяет для ускорения инициализации листа свойств.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Включение приложения фокус ввода для элемента управления в окне свойств. Если `OnInitDialog` возвращает ненулевое Windows устанавливает фокус ввода на первый элемент управления в окне свойств. Приложение может возвращать значение 0 только в том случае, если он задан явно фокус ввода для элемента управления в окне свойств.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается в ответ на сообщение WM_INITDIALOG. Это сообщение отправляется в окно свойств во время [создать](#create) или [DoModal](#domodal) вызовы, которые происходят непосредственно перед выводом страницы свойств.  
  
 Переопределите эту функцию-член, если необходимо выполнить специальную обработку при инициализации страницы свойств. В переопределенная версия вызвать метод базового класса `OnInitDialog` , но не принимать во внимание его возвращаемое значение. Обычно вернет **TRUE** из функции переопределенному члену.  
  
 Не обязательно записи схемы сообщений для этой функции-члена.  
  
##  <a name="pressbutton"></a>  CPropertySheet::PressButton  
 Имитирует Выбор указанной кнопки в окне свойств.  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>Параметры  
 *nButton*  
 nButton: Определяет нажатие кнопки. Этот параметр может принимать одно из следующих значений:  
  
- **PSBTN_BACK** нажимает кнопку "Назад".  
  
- **PSBTN_NEXT** нажимает кнопку "Далее".  
  
- **PSBTN_FINISH** нажимает кнопку "Готово".  
  
- **PSBTN_OK** выбирает кнопки «ОК».  
  
- **PSBTN_APPLYNOW** нажимает кнопку Применить.  
  
- **PSBTN_CANCEL** нажимает кнопку "Отмена".  
  
- **PSBTN_HELP** нажимает кнопку "Справка".  
  
### <a name="remarks"></a>Примечания  
 В разделе [PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) Дополнительные сведения о сообщении Windows SDK Pressbutton.  
  
 Вызов `PressButton` не будет отправлять [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) уведомления через страницу свойств для платформы. Чтобы посылать уведомления, вызовите [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>  CPropertySheet::RemovePage  
 Удаляет страницу из страницы свойств, а также уничтожает соответствующее окно.  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 *Физ_страница*  
 Указывает на страницу, чтобы удалить из таблицы свойств. Не может быть `NULL`.  
  
 *nPage*  
 Индекс страницы должны быть удалены. Должен быть между 0 и меньше, чем количество страниц в окне свойств, включительно.  
  
### <a name="remarks"></a>Примечания  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md) сам объект не уничтожается, пока владелец `CPropertySheet` закрытия окна.  
  
##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage  
 Изменение активной странице.  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 *nPage*  
 Индекс страницы для задания. Он должен быть между 0 и меньше, чем количество страниц в окне свойств, включительно.  
  
 *Физ_страница*  
 Указывает на страницу, чтобы задать в окне свойств. Он не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств активирован успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Например, использовать `SetActivePage` Если действие пользователя на одной странице должна вызывать другую страницу стать активной странице.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText  
 Задает текст в команду "Готово".  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszText*  
 Указывает текст, который отображается на команду "Готово".  
  
### <a name="remarks"></a>Примечания  
 Вызовите `SetFinishText` для отображения текста кнопки Готово и скрытия кнопки Далее и назад, пользователь не завершит работу на последней странице мастера.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="settitle"></a>  CPropertySheet::SetTitle  
 Указывает заголовок страницы свойств (текст, отображаемый в строке заголовка окна фрейма).  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *nStyle*  
 Задает стиль заголовка листа свойств. Стиль должен быть указан по 0 или в виде **PSH_PROPTITLE**. Если стиль имеет значение как **PSH_PROPTITLE**, после текста, указанного в качестве заголовка отображается слово «Свойства». Например, вызов `SetTitle`(«Простой», **PSH_PROPTITLE**) приведет к заголовок листа свойств из «Простого свойства».  
  
 *lpszText*  
 Указывает текст для использования в качестве заголовка в заголовке окна свойств.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию окна свойств используется параметр заголовка в конструкторе листа свойств.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons  
 Включает или отключает кнопку "Назад", "Next" или "Готово" в окне свойств мастера.  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwFlags*  
 Набор флагов, позволяющих настраивать функции и внешний вид кнопок мастера. Этот параметр может быть сочетанием следующих значений:  
  
- **PSWIZB_BACK** кнопка "Назад"  
  
- **PSWIZB_NEXT** рядом кнопку  
  
- **PSWIZB_FINISH** кнопку "Готово"  
  
- **PSWIZB_DISABLEDFINISH** кнопки Готово отключено  
  
### <a name="remarks"></a>Примечания  
 Вызовите `SetWizardButtons` только в том случае, когда открыта диалогового окна; не удается вызвать `SetWizardButtons` перед вызовом метода [DoModal](#domodal). Как правило, следует вызывать `SetWizardButtons` из [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).  
  
 Если назад один раз кнопок пользователя и вы хотите изменить текст на "Готово" или скрыть следующего завершения мастера вызова [SetFinishText](#setfinishtext). Обратите внимание, что та же кнопка совместно для завершения и далее. Можно отобразить о завершении или кнопку Далее за один раз, но не оба.  
  
### <a name="example"></a>Пример  
 Объект `CPropertySheet` содержит три страницы свойств мастера: `CStylePage`, `CColorPage`, и `CShapePage`.  В следующем фрагменте кода показано, как включить и отключить **обратно** и **Далее** кнопки на странице свойств мастера.  
  
 [!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode  
 Устанавливает в качестве мастер страницы свойств.  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Примечания  
 Основной характеристикой мастер страницы свойств заключается в том пользователь переходит с помощью рядом или Готово, резервное Отмена кнопок вместо символов табуляции.  
  
 Вызовите `SetWizardMode` перед вызовом [DoModal](#domodal). После вызова метода `SetWizardMode`, `DoModal` будет возвращать либо **ID_WIZFINISH** (если пользователь не закроет с помощью кнопки "Готово") или **IDCANCEL**.  
  
 `SetWizardMode` Устанавливает флаг PSH_WIZARD.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Пример MFC: SNAPVW](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



