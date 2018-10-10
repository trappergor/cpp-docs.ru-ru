---
title: Класс CPropertySheet | Документация Майкрософт
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
ms.openlocfilehash: 50b1816320521f8ad20ee64fc4a051f938e902ec
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890781"
---
# <a name="cpropertysheet-class"></a>Cpropertysheet-класс

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
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Указывает, использует ли окно свойств с накоплением "или" scrolling вкладки.|
|[CPropertySheet::EndDialog](#enddialog)|Завершает окно свойств.|
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Извлекает индекс активной страницы свойств.|
|[CPropertySheet::GetActivePage](#getactivepage)|Возвращает объект активной страницей.|
|[CPropertySheet::GetPage](#getpage)|Извлекает указатель на указанную страницу.|
|[CPropertySheet::GetPageCount](#getpagecount)|Возвращает число страниц в окне свойств.|
|[CPropertySheet::GetPageIndex](#getpageindex)|Возвращает индекс заданной страницы свойств.|
|[CPropertySheet::GetTabControl](#gettabcontrol)|Извлекает указатель на элемент управления вкладками.|
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Преобразует единицы диалогового окна прямоугольник в единицы экрана.|
|[CPropertySheet::OnInitDialog](#oninitdialog)|Переопределите для ускорения инициализации листа свойств.|
|[CPropertySheet::PressButton](#pressbutton)|Имитирует Выбор указанную кнопку в окне свойств.|
|[CPropertySheet::RemovePage](#removepage)|Удаляет страницу из таблицы свойств.|
|[CPropertySheet::SetActivePage](#setactivepage)|Программным образом задается следующий объект активной страницей.|
|[CPropertySheet::SetFinishText](#setfinishtext)|Задает текст для кнопки «Готово».|
|[CPropertySheet::SetTitle](#settitle)|Задает заголовок страницы свойств.|
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Позволяет кнопок мастера.|
|[CPropertySheet::SetWizardMode](#setwizardmode)|Включает режим мастера.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) структуры. Предоставляет доступ к основным свойством параметров таблицы стилей.|

## <a name="remarks"></a>Примечания

Страница свойств состоит из `CPropertySheet` объекта и один или несколько [CPropertyPage](../../mfc/reference/cpropertypage-class.md) объектов. Платформа отображает страницу свойств, как окно с набором вкладку индексов и область, которая содержит текущую страницу. Пользователь переходит к определенной странице, используя соответствующую вкладку.

`CPropertySheet` обеспечивает поддержку расширенный [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) структура, представленная в Windows 98 и 2000, Windows NT. Эта структура содержит дополнительные флаги и члены, которые поддерживают использование изображение «водяной знак».

Чтобы отобразить эти новые образы автоматически в ваш объект страницы свойств, передайте допустимые значения для точечного рисунка и палитру изображений в вызове [CPropertySheet::Construct](#construct) или [CPropertySheet::CPropertySheet](#cpropertysheet).

Несмотря на то что `CPropertySheet` не является производным от [CDialog](../../mfc/reference/cdialog-class.md), управление `CPropertySheet` объект аналогичен управление `CDialog` объекта. Например, создание свойств требуется для создания двух частей: вызовите конструктор, а затем вызвать [DoModal](#domodal) для модальную страницу свойств или [создать](#create) для немодальный лист свойств. `CPropertySheet` Существует два типа конструкторов: [CPropertySheet::Construct](#construct) и [CPropertySheet::CPropertySheet](#cpropertysheet).

При построении `CPropertySheet` объекта, некоторые [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) вызовет исключение первого шанса возникает. В результате из системы, попытка изменить стиль свойств перед созданием таблицы стилей. Чтобы избежать этого исключения, убедитесь, что вы установлены следующие стили при создании вашей `CPropertySheet`:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Следующие стили являются необязательными и не вызовет исключения первого шанса:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Любой другой `Window Styles` запрещен и их не следует включить.

Обмен данными между `CPropertySheet` объекта и внешнего объекта похож на обмен данными с `CDialog` объекта. Важное отличие заключается, что параметры свойств как правило, переменные-члены `CPropertyPage` объектов, а не из `CPropertySheet` сам объект.

Можно создать тип вкладки диалогового окна вызывается мастер, который состоит из свойств последовательностью страницы свойств, которые проводят пользователя через шаги операции, такие как Настройка устройства или создание информационного бюллетеня. В диалоговом окне вкладку тип мастера на страницах свойств не имеют вкладки и только одно свойство страница видна за раз. Кроме того, вместо того, **ОК** и **применить** имеет кнопки, диалоговое окно вкладки мастера **обратно** кнопки **Далее** или  **Готово** кнопки **отменить** кнопку и **помочь** кнопки.

Чтобы создать диалоговое окно мастера, выполните те же действия, которые необходимо выполнить для создания стандартных свойств, но вызывает [SetWizardMode](#setwizardmode) перед вызовом метода [DoModal](#domodal). Чтобы включить кнопок мастера, вызовите [SetWizardButtons](#setwizardbuttons), используя флаги для настройки их функциональности и внешнему виду. Чтобы включить **Готово** "Кнопка", вызовите [SetFinishText](#setfinishtext) после пользователя были предприняты никакие меры на последней странице мастера.

Дополнительные сведения об использовании `CPropertySheet` объектов, см. в статье [вкладки свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="addpage"></a>  CPropertySheet::AddPage

Добавляет предоставленный страницы с крайняя вкладка в окне свойств.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
Указывает на страницу, чтобы добавить в лист свойств. Не может принимать значение NULL.

### <a name="remarks"></a>Примечания

Добавьте страницы свойств в порядке слева направо, который будет отображаться.

`AddPage` Добавляет [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) объект `CPropertySheet` объект в список страниц, но не создает фактически окна для страницы. Платформа откладывает Создание окна для страницы, пока пользователь не выберет этой страницы.

При добавлении страницы свойств с помощью `AddPage`, `CPropertySheet` является родительским для объекта `CPropertyPage`. Чтобы получить доступ к странице свойств на странице свойств, вызовите [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).

Нет необходимости ждать до создания окна страницы свойств для вызова `AddPage`. Как правило, вы будете вызывать `AddPage` перед вызовом [DoModal](#domodal) или [создать](#create).

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

*nIDCaption*<br/>
Идентификатор заголовка, который будет использоваться для страницы свойств.

*pParentWnd*<br/>
Указатель на родительское окно страницы свойств. Если значение равно NULL, родительское окно будет главное окно приложения.

*iSelectPage*<br/>
Индекс страницы, которая изначально будет находиться в начале списка. По умолчанию используется первая страница, добавленная в выбранную таблицу.

*pszCaption*<br/>
Указатель на строку, содержащую заголовок, используемый для страницы свойств. Не может принимать значение NULL.

*hbmWatermark*<br/>
Дескриптор растрового изображения водяного знака страницы свойств.

*hpalWatermark*<br/>
Дескриптор палитра растрового изображения водяного знака и/или растрового изображения заголовка.

*hbmHeader*<br/>
Дескриптор точечного рисунка заголовка страницы свойств.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член, если один из конструкторов класса уже не был вызван. Например, вызвать `Construct` при объявлении или выделить массивы из `CPropertySheet` объектов. В случае массивов, необходимо вызвать метод `Construct` для каждого элемента в массиве.

Чтобы открыть окно свойств, вызовите [DoModal](#domodal) или [создать](#create). Строка, содержащаяся в первом параметре помещаются в строке заголовка для страницы свойств.

Можно отобразить изображения водяного знака и заголовка автоматически при использовании прототипов третьего или четвертого `Construct`, перечисленных выше, и передайте допустимые значения *hbmWatermark*, *hpalWatermark* , и/или *hbmHeader* параметров.

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

*nIDCaption*<br/>
Идентификатор заголовка, который будет использоваться для страницы свойств.

*pParentWnd*<br/>
Точки в родительское окно страницы свойств. Если значение равно NULL, родительское окно будет главное окно приложения.

*iSelectPage*<br/>
Индекс страницы, которая изначально будет находиться в начале списка. По умолчанию используется первая страница, добавленная в выбранную таблицу.

*pszCaption*<br/>
Указывает строку, содержащую заголовок, используемый для страницы свойств. Не может принимать значение NULL.

*hbmWatermark*<br/>
Дескриптор точечного рисунка фона страницы свойств.

*hpalWatermark*<br/>
Дескриптор палитры растрового изображения водяного знака и/или растрового изображения заголовка.

*hbmHeader*<br/>
Дескриптор к растровому изображению заголовка страницы свойств.

### <a name="remarks"></a>Примечания

Чтобы открыть окно свойств, вызовите [DoModal](#domodal) или [создать](#create). Строка, содержащаяся в первом параметре помещаются в строке заголовка для страницы свойств.

Если у вас есть несколько параметров (например, если вы используете массив), используйте [создания](#construct) вместо `CPropertySheet`.

Можно отобразить изображения водяного знака и заголовка автоматически при использовании прототипов третьего или четвертого `CPropertySheet`выше, и передайте допустимые значения для *hbmWatermark*, *hpalWatermark*, и / или *hbmHeader* параметров.

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

*pParentWnd*<br/>
Указатель на родительское окно. Если значение равно NULL, родительским является рабочий стол.

*dwStyle*<br/>
Стили окна для страницы свойств. Полный список доступных стилей, см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwExStyle*<br/>
Расширенные стили окна для страницы свойств. Полный список доступных стилей, см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если окно свойств создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов `Create` может быть внутри конструктора или его можно вызывать после вызова конструктора.

Стиль по умолчанию, выраженный, передав значение -1 как *dwStyle*, является фактически WS_SYSMENU&#124;WS_POPUP&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;WS_VISIBLE. Значение по умолчанию расширенный стиль окна, выраженный путем передачи 0 как *dwExStyle*, является фактически WS_EX_DLGMODALFRAME.

`Create` Функция-член возвращает сразу после создания страницы свойств. Чтобы уничтожить окно свойств, вызовите [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).

Немодальные свойств, отображаемых с помощью вызова `Create` не имеют кнопки ОК, Отмена, применить и справки как модальное свойств. Нужные кнопки должны создаваться пользователем.

Чтобы отобразить модальную страницу свойств, вызовите [DoModal](#domodal) вместо этого.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

##  <a name="domodal"></a>  CPropertySheet::DoModal

Отображает модальную страницу свойств.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK и IDCANCEL, если функция выполнена успешно; в противном случае — 0 или -1. Если окно свойств установлено в качестве мастера (см. в разделе [SetWizardMode](#setwizardmode)), `DoModal` возвращает ID_WIZFINISH или IDCANCEL.

### <a name="remarks"></a>Примечания

Возвращаемое значение соответствует идентификатор элемента управления, если оно закрыто окно свойств. После возврата этой функции, windows, соответствующее окно свойств и все страницы будут уничтожены. Сами объекты по-прежнему будет существовать. Как правило, вы получите данные из [CPropertyPage](../../mfc/reference/cpropertypage-class.md) объектов после `DoModal` возвращает IDOK.

Чтобы отобразить безмодальной вкладки свойства, вызовите [создать](#create) вместо этого.

При создании страницы свойств из его соответствующий ресурс диалогового окна, это может вызвать исключения первого шанса. В результате на странице свойств, изменив стиль ресурса диалогового окна необходимый стиль, перед созданием страницы. Из-за ресурсов доступны только для чтения, в результате исключения. Система обрабатывает исключение и создается копия измененного ресурса. Исключения первого шанса может игнорироваться.

> [!NOTE]
>  Это исключение должно обрабатываться операционной системой, при компиляции с помощью модели асинхронной обработки исключений. Дополнительные сведения о модели обработки исключений см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md). В этом случае не создают оболочки для вызовов `CPropertySheet::DoModal` с помощью блока try-catch C++ в котором catch обрабатывает все исключения, например `catch (...)`. Этот блок будет обрабатывать исключения, предназначены для операционной системы и причину непредсказуемое поведение. Тем не менее можно безопасно использовать обработки исключения определенных типов или структурированная обработка исключений, где исключение нарушения прав доступа передается через операционную систему исключений C++.

Чтобы избежать возникновения этого исключения первого шанса, вы можете вручную гарантировать что свойств имеет правильные [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). Необходимо задать следующие стили для страницы свойств:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Можно использовать следующие необязательные стили не вызывая исключения первого шанса:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Отключите все другие стили Windows, так как они не совместимы со страницами свойств. Это не применяется к расширенные стили. Правильную настройку этих стандартных стилей гарантирует, что окно свойств не нужно изменять и позволит избежать создания исключения первого шанса.

### <a name="example"></a>Пример

См. в примере [CPropertySheet::AddPage](#addpage).

##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs

Указывает, следует ли стека строк вкладок в окне свойств.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Параметры

*bStacked*<br/>
Указывает, включены ли с накоплением вкладок в окне свойств. Отключить, задав с накоплением строк тегов *bStacked* значение false.

### <a name="remarks"></a>Примечания

По умолчанию Если лист свойств содержит несколько вкладок, чем может поместиться в одной строке на ширину страницы свойств, вкладки будет стека во множестве строк. Чтобы использовать прокрутки вкладок вместо наложения вкладок, вызовите `EnableStackedTabs` с *bStacked* равным FALSE перед вызовом [DoModal](#domodal) или [создать](#create).

Необходимо вызвать `EnableStackedTabs` при создании модального или немодального свойств. Чтобы включить этот стиль в `CPropertySheet`-производный класс, написать обработчик сообщений для сообщений WM_CREATE. В переопределенной версии [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), вызовите `EnableStackedTabs( FALSE )` до вызова реализации базового класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

##  <a name="enddialog"></a>  CPropertySheet::EndDialog

Завершает окно свойств.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Параметры

*nEndID*<br/>
Идентификатор для использования в качестве возвращаемого значения свойств.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается платформой при нажатии ОК, Отмена или кнопка "Закрыть". Вызов, что эта функция-член, если происходит событие, которое следует закрыть окно свойств.

Эта функция-член используется только с модальным диалоговым окном.

### <a name="example"></a>Пример

См. в примере [CPropertySheet::PressButton](#pressbutton).

##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex

Получает индекс активной странице окно свойств, а затем использует возвращенный номер индекса параметром для `GetPage`.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс активной страницей.

### <a name="example"></a>Пример

См. в примере [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage

Извлекает окно свойств активной страницей.

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

*nPage*<br/>
Индекс нужную страницу, начиная с 0. Должно быть между 0 и меньше, чем количество страниц в окне свойств, включительно.

### <a name="return-value"></a>Возвращаемое значение

Указатель на страницы, соответствующий *nPage* параметра.

### <a name="example"></a>Пример

См. в примере [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount

Определяет число страниц в настоящее время в окне свойств.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество страниц в окне свойств.

### <a name="example"></a>Пример

См. в примере [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex

Возвращает индекс заданной страницы на странице свойств.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
Указывает страницу с индексом, который требуется найти. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Номер индекса страницы.

### <a name="remarks"></a>Примечания

Например, можно использовать `GetPageIndex` для получения индекса страницы, чтобы использовать [SetActivePage](#setactivepage) или [GetPage](#getpage).

### <a name="example"></a>Пример

См. в примере [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl

Извлекает указатель на набор вкладок, чтобы сделать нечто, относящееся к элементу управления вкладки (то есть для использования этих интерфейсов API в [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент управления вкладками.

### <a name="remarks"></a>Примечания

Например можно Вызовите эту функцию-член, если вы хотите добавить каждой из вкладок растровых изображений во время инициализации.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

##  <a name="m_psh"></a>  CPropertySheet::m_psh

Структуры, члены которой хранения характеристики [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2).

### <a name="remarks"></a>Примечания

Эта структура используется для инициализации внешний вид страницы свойств после его создания, но перед его отображением с [DoModal](#domodal) функция-член. Например, задать *dwSize* членом `m_psh` до размера требуется иметь свойств.

Дополнительные сведения об этой структуре, включая список его элементов см. в разделе PROPSHEETHEADER в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect

Преобразует единицы диалогового окна прямоугольник в единицы экрана.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указывает на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , диалоговое окно содержит координаты для преобразования.

### <a name="remarks"></a>Примечания

Единицы диалогового окна сформулирована в терминах текущего диалогового окна базовой единицей, производных от среднюю ширину и высоту символов в шрифте, используемый для текста диалогового окна. Одна единица — одной четвертой единицы базы нулевой ширины диалогового окна, а одна единица — одну восьмую высота основы единицы диалогового окна.

[GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows функция возвращает сведения о размере для системного шрифта, но при использовании DS_SETFONT стиль в файле определения ресурса можно указать другой шрифт для каждой страницы свойств. [MapDialogRect](/windows/desktop/api/winuser/nf-winuser-mapdialogrect) функции Windows, описанной в пакете Windows SDK, использует соответствующий шрифт для этого диалогового окна.

`MapDialogRect` Функция-член заменяет единицы диалогового окна в *lpRect* с экрана единицы (в пикселях), чтобы прямоугольник можно использовать для создания диалогового окна или размещения элемента управления в поле.

##  <a name="oninitdialog"></a>  CPropertySheet::OnInitDialog

Переопределяет для дополнения инициализации листа свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Указывает, ли приложение устанавливает фокус ввода к одному из элементов управления в окне свойств. Если `OnInitDialog` возвращает ненулевое значение, Windows устанавливает фокус ввода на первый элемент управления в окне свойств. Приложение может возвращать значение 0 только в том случае, если он задан явно фокус ввода к одному из элементов управления в окне свойств.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается в ответ на сообщение WM_INITDIALOG. Это сообщение отправляется в окно свойств во время [создать](#create) или [DoModal](#domodal) вызовы, которые происходят непосредственно перед отображается окно свойств.

Переопределите эту функцию-член, если вам нужно выполнять специальную обработку при инициализации страницы свойств. В переопределенные версии, необходимо сначала вызвать базовый класс `OnInitDialog` , но игнорируйте его возвращаемое значение. Обычно из функции переопределенным членом возвратит TRUE.

Запись схемы сообщений не обязательно для этой функции-члена.

##  <a name="pressbutton"></a>  CPropertySheet::PressButton

Имитирует Выбор указанную кнопку в окне свойств.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>Параметры

*nButton*<br/>
nButton: Определяет нажатие кнопки. Этот параметр может принимать одно из следующих значений:

- PSBTN_BACK нажимает кнопку "Назад".

- PSBTN_NEXT выбирает "Далее".

- PSBTN_FINISH нажимает кнопку "Готово".

- PSBTN_OK выбирает "ОК".

- PSBTN_APPLYNOW выбирает кнопка "Применить".

- PSBTN_CANCEL нажимает кнопку "Отмена".

- PSBTN_HELP нажимает кнопку "Справка".

### <a name="remarks"></a>Примечания

См. в разделе [PSM_PRESSBUTTON](/windows/desktop/Controls/psm-pressbutton) Дополнительные сведения о сообщении Pressbutton пакета SDK для Windows.

Вызов `PressButton` не будет отправлять [PSN_APPLY](/windows/desktop/Controls/psn-apply) уведомление через страницу свойств для платформы. Для отправки уведомления, вызывать [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

##  <a name="removepage"></a>  CPropertySheet::RemovePage

Удаляет страницу из таблицы свойств и уничтожает соответствующее окно.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
Указывает на страницу, чтобы удалить из таблицы свойств. Не может принимать значение NULL.

*nPage*<br/>
Индекс страницы для удаления. Должно быть между 0 и меньше, чем количество страниц в окне свойств, включительно.

### <a name="remarks"></a>Примечания

[CPropertyPage](../../mfc/reference/cpropertypage-class.md) пока владелец не уничтожается сам объект `CPropertySheet` окно закрыто.

##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage

Изменяет активной страницей.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*nPage*<br/>
Индекс страницы для задания. Он должен быть между 0 и меньше, чем количество страниц в окне свойств, включительно.

*Физ_страница*<br/>
Указывает страницу, чтобы задать в окне свойств. Он не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если окно свойств активирован успешно. в противном случае 0.

### <a name="remarks"></a>Примечания

Например, использовать `SetActivePage` Если действия пользователя на одной странице следует вызывать другую страницу стать активной страницей.

### <a name="example"></a>Пример

См. в примере [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText

Задает текст в команду "Готово".

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указывает на текст, отображаемый на команду "Готово".

### <a name="remarks"></a>Примечания

Вызовите `SetFinishText` для отображения текста "Готово", команда и скрыть кнопки следующего и обратно, как только пользователь завершит работу на последней странице мастера.

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

*nStyle*<br/>
Задает стиль заголовка листа свойств. Необходимо указать стиль, на 0 или как PSH_PROPTITLE. Если стиль имеет значение как PSH_PROPTITLE, слово «Свойства» отображается после текста, указанный в качестве заголовка. Например, вызов `SetTitle`(«Simple», PSH_PROPTITLE) приведет к заголовок таблицы свойства «Простых свойств».

*lpszText*<br/>
Указывает на текст для использования в качестве заголовка в заголовке окна свойств.

### <a name="remarks"></a>Примечания

По умолчанию страницу свойств используется параметр заголовка в конструкторе листа свойств.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons

Включает или отключает кнопку "Назад", "Next" или "Готово" в окне свойств мастера.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Набор флагов, которые настраивать функции и внешний вид кнопок мастера. Этот параметр может быть сочетанием следующих значений:

- Кнопка PSWIZB_BACK назад

- Кнопка "Далее PSWIZB_NEXT"

- Кнопки Готово PSWIZB_FINISH

- Кнопка PSWIZB_DISABLEDFINISH отключенные Готово

### <a name="remarks"></a>Примечания

Вызовите `SetWizardButtons` только после диалоговое окно открытым, а вы не можете вызвать `SetWizardButtons` перед вызовом метода [DoModal](#domodal). Как правило, следует вызывать `SetWizardButtons` из [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).

Если назад один раз кнопок пользователя и вы хотите изменить текст "Готово", или скрыть следующего завершения мастера вызов [SetFinishText](#setfinishtext). Обратите внимание на то, что та же кнопка используется совместно Готово и далее. Можно отобразить окончания или кнопка "Далее" за один раз, но не оба.

### <a name="example"></a>Пример

Объект `CPropertySheet` содержит три страницы свойств мастера: `CStylePage`, `CColorPage`, и `CShapePage`.  В следующем фрагменте кода показано, как включить и отключить **обратно** и **Далее** кнопки на странице мастера.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode

Устанавливает в качестве мастер страницы свойств.

```
void SetWizardMode();
```

### <a name="remarks"></a>Примечания

Основной характеристикой свойства страницы мастера является пользователь переходит с помощью рядом или Готово, обратно что кнопки вместо вкладок отмены.

Вызовите `SetWizardMode` перед вызовом [DoModal](#domodal). После вызова метода `SetWizardMode`, `DoModal` возвратит ID_WIZFINISH (если пользователь закрывает с помощью кнопки «Готово») или IDCANCEL.

`SetWizardMode` Устанавливает флаг PSH_WIZARD.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>См. также

[Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)<br/>
[Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)<br/>
[Пример MFC PROPDLG](../../visual-cpp-samples.md)<br/>
[Пример MFC: SNAPVW](../../visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
