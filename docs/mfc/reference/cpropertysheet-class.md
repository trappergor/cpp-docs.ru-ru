---
title: Класс CPropertySheet
ms.date: 11/04/2016
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
ms.openlocfilehash: edae0e3d4751461bc8a5eb6644f5fdc62b0a5e8a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916859"
---
# <a name="cpropertysheet-class"></a>Класс CPropertySheet

Представляет страницы свойств, также известные как диалоговые окна вкладки.

## <a name="syntax"></a>Синтаксис

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPropertySheet:: CPropertySheet](#cpropertysheet)|Создает объект `CPropertySheet`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPropertySheet:: AddPage](#addpage)|Добавляет страницу в таблицу свойств.|
|[CPropertySheet:: конструкция](#construct)|Создает объект `CPropertySheet`.|
|[CPropertySheet:: Create](#create)|Отображает немодальную страницу свойств.|
|[CPropertySheet::D Омодал](#domodal)|Отображает модальную страницу свойств.|
|[CPropertySheet:: Енаблестаккедтабс](#enablestackedtabs)|Указывает, использует ли страница свойств вкладки с накоплением или прокруткой.|
|[CPropertySheet:: EndDialog](#enddialog)|Завершает работу страницы свойств.|
|[CPropertySheet:: Жетактивеиндекс](#getactiveindex)|Получает индекс активной страницы вкладки свойств.|
|[CPropertySheet:: Жетактивепаже](#getactivepage)|Возвращает активный объект страницы.|
|[CPropertySheet:: @ Page](#getpage)|Извлекает указатель на указанную страницу.|
|[CPropertySheet:: Жетпажекаунт](#getpagecount)|Извлекает количество страниц в таблице свойств.|
|[CPropertySheet:: Жетпажеиндекс](#getpageindex)|Извлекает индекс указанной страницы вкладки свойств.|
|[CPropertySheet::, TabControl](#gettabcontrol)|Извлекает указатель на элемент управления "Вкладка".|
|[CPropertySheet:: Мапдиалогрект](#mapdialogrect)|Преобразует единицы диалогового окна прямоугольника в единицы экрана.|
|[CPropertySheet:: Онинитдиалог](#oninitdialog)|Переопределите для расширения инициализации страницы свойств.|
|[CPropertySheet::P Рессбуттон](#pressbutton)|Имитирует выбранную кнопку на странице свойств.|
|[CPropertySheet:: RemovePage](#removepage)|Удаляет страницу из страницы свойств.|
|[CPropertySheet:: Сетактивепаже](#setactivepage)|Программно задает активный объект Page.|
|[CPropertySheet:: Сетфиништекст](#setfinishtext)|Задает текст для кнопки Готово.|
|[CPropertySheet:: Сеттитле](#settitle)|Задает заголовок страницы свойств.|
|[CPropertySheet:: Сетвизардбуттонс](#setwizardbuttons)|Включает кнопки мастера.|
|[CPropertySheet:: Сетвизардмоде](#setwizardmode)|Включает режим мастера.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CPropertySheet:: m_psh](#m_psh)|Структура [Пропшисеадер](/windows/desktop/api/prsht/ns-prsht-propsheetheadera_v2) Windows. Предоставляет доступ к базовым параметрам страницы свойств.|

## <a name="remarks"></a>Примечания

Страница свойств состоит из `CPropertySheet` объекта и одного или нескольких объектов [CPropertyPage](../../mfc/reference/cpropertypage-class.md) . Платформа отображает страницу свойств в виде окна с набором индексов вкладок и областью, которая содержит текущую выбранную страницу. Пользователь переходит на определенную страницу с помощью соответствующей вкладки.

`CPropertySheet`обеспечивает поддержку расширенной структуры [пропшисеадер](/windows/desktop/api/prsht/ns-prsht-propsheetheadera_v2) , представленной в Windows 98 и windows NT 2000. Структура содержит дополнительные флаги и члены, поддерживающие использование фонового рисунка "водяного знака".

Чтобы автоматически отображать эти новые изображения в объекте страницы свойств, передайте допустимые значения для изображений битовой карты и палитры в вызове [CPropertySheet:: конструировать](#construct) или [CPropertySheet:: CPropertySheet](#cpropertysheet).

Несмотря `CPropertySheet` на то, что не является производным от `CPropertySheet` [CDialog](../../mfc/reference/cdialog-class.md), управление объектом аналогично управлению `CDialog` объектом. Например, создание страницы свойств требует создания двух частей: вызов конструктора, а затем вызов [DoModal](#domodal) для модальной страницы свойств или [CREATE](#create) для немодальной страницы свойств. `CPropertySheet`имеет два типа конструкторов: [CPropertySheet:: конструировать](#construct) и [CPropertySheet:: CPropertySheet](#cpropertysheet).

При создании `CPropertySheet` объекта некоторые [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) могут привести к возникновению первого шанса исключения. В результате система пытается изменить стиль страницы свойств до создания листа. Чтобы избежать этого исключения, убедитесь, что заданы следующие стили при создании `CPropertySheet`:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Следующие стили являются необязательными и не будут вызывать исключение First-шанса:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Любые другие `Window Styles` запрещены, и их не следует включать.

Обмен данными между `CPropertySheet` объектом и внешним объектом аналогичен обмену данными `CDialog` с объектом. Важное отличие состоит в том, что параметры страницы свойств обычно являются переменными `CPropertyPage` -членами объектов, а не `CPropertySheet` самим объектом.

Можно создать диалоговое окно типа «вкладка», которое состоит из страницы свойств с последовательностью страниц свойств, которые позволяют пользователю выполнить шаги операции, такие как Настройка устройства или создание информационного бюллетеня. В диалоговом окне Вкладка «тип мастера» страницы свойств не имеют вкладок и только одна страница свойств видна за раз. Кроме того, вместо того, **ОК** и **применить** имеет кнопки, диалоговое окно вкладки мастера **обратно** кнопки **Далее** или **Готово** кнопки **отменить** кнопку и **помочь** кнопки.

Чтобы создать диалоговое окно "тип мастера", выполните те же действия, что и при создании стандартной вкладки свойств, но вызовите [сетвизардмоде](#setwizardmode) перед вызовом [DoModal](#domodal). Чтобы включить кнопки мастера, вызовите [сетвизардбуттонс](#setwizardbuttons), используя флаги для настройки их функции и внешнего вида. Чтобы включить кнопку **"Готово"** , вызовите [сетфиништекст](#setfinishtext) после того, как пользователь выполнил действие на последней странице мастера.

Дополнительные сведения об использовании `CPropertySheet` объектов см. в статьях свойства статьи [и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс. h

##  <a name="addpage"></a>CPropertySheet:: AddPage

Добавляет предоставляемую страницу с крайней правой вкладкой на странице свойств.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*ппаже*<br/>
Указывает на страницу, которую необходимо добавить на вкладку свойств. Не может принимать значение NULL.

### <a name="remarks"></a>Примечания

Добавьте страницы на страницу свойств в порядке слева направо, чтобы они отображались.

`AddPage`Добавляет объект [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) в список страниц `CPropertySheet` объекта, но на самом деле не создает окно для страницы. Платформа откладывает создание окна для страницы до тех пор, пока пользователь не выберет эту страницу.

При добавлении страницы свойств с помощью `AddPage` `CPropertySheet` свойство `CPropertyPage`является родительским для. Чтобы получить доступ к странице свойств со страницы свойств, вызовите [CWnd::-Parent](../../mfc/reference/cwnd-class.md#getparent).

Не нужно ждать, пока создается окно страницы свойств для вызова `AddPage`. Как правило, вызов `AddPage` выполняется перед вызовом [DoModal](#domodal) или [CREATE](#create).

При вызове `AddPage` после отображения страницы свойств в строке табуляции будет отражена только что добавленная страница.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

##  <a name="construct"></a>CPropertySheet:: конструкция

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

*нидкаптион*<br/>
ИДЕНТИФИКАТОР заголовка, который будет использоваться для страницы свойств.

*ппарентвнд*<br/>
Указатель на родительское окно страницы свойств. Если значение равно NULL, то родительское окно будет основным окном приложения.

*иселектпаже*<br/>
Индекс страницы, которая изначально будет находиться в начале. По умолчанию — первая страница, добавленная на лист.

*псзкаптион*<br/>
Указатель на строку, содержащую заголовок, который будет использоваться для страницы свойств. Не может принимать значение NULL.

*хбмватермарк*<br/>
Маркер для изображения водяного знака страницы свойств.

*хпалватермарк*<br/>
Маркер для палитры битовой карты подложки и/или битовой карты заголовка.

*хбмхеадер*<br/>
Обработайте с битовой картой заголовка страницы свойств.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию члена, если один из конструкторов класса еще не вызывался. Например, вызовите `Construct` метод при объявлении или выделении `CPropertySheet` массивов объектов. В случае массивов необходимо вызывать `Construct` для каждого элемента в массиве.

Чтобы отобразить страницу свойств, вызовите [DoModal](#domodal) или [CREATE](#create). Строка, содержащаяся в первом параметре, будет помещена в строку заголовка для страницы свойств.

Вы можете автоматически отображать водяные знаки и/или изображения заголовков, если вы используете третий или `Construct`четвертый прототипы, перечисленные выше, и передаете допустимые значения для параметров *хбмватермарк*, *хпалватермарк*и/или *хбмхеадер* .

### <a name="example"></a>Пример

В следующем примере демонстрируется, в каких обстоятельствах следует `Construct`вызывать.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

##  <a name="cpropertysheet"></a>CPropertySheet:: CPropertySheet

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

*нидкаптион*<br/>
ИДЕНТИФИКАТОР заголовка, который будет использоваться для страницы свойств.

*ппарентвнд*<br/>
Указывает на родительское окно страницы свойств. Если значение равно NULL, то родительское окно будет основным окном приложения.

*иселектпаже*<br/>
Индекс страницы, которая изначально будет находиться в начале. По умолчанию — первая страница, добавленная на лист.

*псзкаптион*<br/>
Указывает на строку, содержащую заголовок, который будет использоваться для страницы свойств. Не может принимать значение NULL.

*хбмватермарк*<br/>
Маркер фонового рисунка страницы свойств.

*хпалватермарк*<br/>
Маркер для палитры битовой карты подложки и/или битовой карты заголовка.

*хбмхеадер*<br/>
Маркер для битовой карты заголовка страницы свойств.

### <a name="remarks"></a>Примечания

Чтобы отобразить страницу свойств, вызовите [DoModal](#domodal) или [CREATE](#create). Строка, содержащаяся в первом параметре, будет помещена в строку заголовка для страницы свойств.

Если у вас есть несколько параметров (например, если используется массив), используйте [конструкцию](#construct) вместо `CPropertySheet`.

Вы можете автоматически отображать водяные знаки и/или изображения заголовков при использовании третьего или четвертого `CPropertySheet`прототипа выше, а также передавать допустимые значения для параметров *хбмватермарк*, *хпалватермарк*и/или *хбмхеадер* .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

##  <a name="create"></a>CPropertySheet:: Create

Отображает немодальную страницу свойств.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
Указывает на родительское окно. Если значение равно NULL, то родительским объектом является Рабочий стол.

*двстиле*<br/>
Стили окна для страницы свойств. Полный список доступных стилей см. в разделе [стили окон](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*двексстиле*<br/>
Расширенные стили окна для страницы свойств. Полный список доступных стилей см. в разделе [Расширенные стили окон](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если страница свойств успешно создана. в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызов `Create` может быть внутри конструктора или вызываться после вызова конструктора.

Стиль по умолчанию, выраженный путем передачи-1 как *двстиле*, фактически&#124;WS_SYSMENU&#124;WS_POPUP&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP WS_VISIBLE. По умолчанию расширенный стиль окна, выраженный путем передачи 0 как *двексстиле*, фактически WS_EX_DLGMODALFRAME.

Функция `Create` – член возвращает сразу после создания страницы свойств. Чтобы уничтожить страницу свойств, вызовите [CWnd::D естройвиндов](../../mfc/reference/cwnd-class.md#destroywindow).

Немодальные страницы свойств, отображаемые `Create` с вызовом, не имеют кнопок "ОК", "Отмена", "Применить сейчас" и "Справка" в качестве модальных страниц свойств. Пользователь должен создать нужные кнопки.

Чтобы отобразить модальную страницу свойств, вызовите [DoModal](#domodal) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

##  <a name="domodal"></a>CPropertySheet::D Омодал

Отображает модальную страницу свойств.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

ИДОК или ИДКАНЦЕЛ, если функция выполнена успешно; в противном случае — 0 или-1. Если страница свойств была установлена как мастер (см. [сетвизардмоде](#setwizardmode)), возвращает либо `DoModal` ID_WIZFINISH, либо идканцел.

### <a name="remarks"></a>Примечания

Возвращаемое значение соответствует ИДЕНТИФИКАТОРу элемента управления, который закрыл вкладку свойств. После возврата этой функции окна, соответствующие странице свойств и всем страницам, будут уничтожены. Сами объекты по-прежнему будут существовать. Как правило, данные из объектов [CPropertyPage](../../mfc/reference/cpropertypage-class.md) будут получены после `DoModal` возвращения идок.

Чтобы отобразить немодальную страницу свойств, вызовите [CREATE](#create) .

При создании страницы свойств из соответствующего ресурса диалогового окна это может привести к возникновению первого шанса исключения. В результате страница свойств изменит стиль ресурса диалогового окна на требуемый стиль перед созданием страницы. Так как ресурсы обычно доступны только для чтения, это вызывает исключение. Система обрабатывает исключение и создает копию измененного ресурса. Поэтому первое исключение может быть проигнорировано.

> [!NOTE]
>  Это исключение должно обрабатываться операционной системой при компиляции с моделью асинхронной обработки исключений. Дополнительные сведения о моделях обработки исключений см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md). В этом случае не следует переносить вызовы в `CPropertySheet::DoModal` с блоком C++ Try-Catch `catch (...)`, в котором Catch обрабатывает все исключения, например. Этот блок обрабатывает исключение, предназначенное для операционной системы, и приводит к непредсказуемому поведению. Однако можно безопасно использовать C++ обработку исключений с конкретными типами исключений или структурной обработкой исключений, в которой исключение нарушения прав доступа передается в операционную систему.

Чтобы избежать возникновения этого первого исключения, можно вручную гарантировать, что страница свойств имеет правильные [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). Необходимо задать следующие стили для страницы свойств:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Можно использовать следующие необязательные стили, не прибегая к возникновению первого шанса исключения:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Отключите все остальные стили Windows, так как они несовместимы со страницами свойств. Это уведомление не относится к расширенным стилям. Правильно устанавливая эти стандартные стили, можно гарантировать, что страница свойств не должна изменяться, и не будет создавать первый экземпляр исключения.

### <a name="example"></a>Пример

См. пример для [CPropertySheet:: addPage](#addpage).

##  <a name="enablestackedtabs"></a>CPropertySheet:: Енаблестаккедтабс

Указывает, следует ли выполнять стек строк вкладок на странице свойств.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Параметры

*бстаккед*<br/>
Указывает, включены ли вкладки с накоплением на странице свойств. Отключите поуровневые строки тегов, установив для *бстаккед* значение false.

### <a name="remarks"></a>Примечания

По умолчанию, если страница свойств содержит больше вкладок, чем помещается в одну строку ширины страницы свойств, то вкладки будут выпадать в несколько строк. Чтобы использовать вкладки с прокруткой вместо вкладок стека, `EnableStackedTabs` вызовите с параметром *бстаккед* со значением false перед вызовом [DoModal](#domodal) или [CREATE](#create).

При создании модальной или немодальной страницы свойств необходимо вызвать метод `EnableStackedTabs` . Чтобы включить этот стиль в `CPropertySheet`производный класс, напишите обработчик сообщений для WM_CREATE. В переопределенной версии [CWnd:: OnCreate](../../mfc/reference/cwnd-class.md#oncreate)вызовите метод `EnableStackedTabs( FALSE )` перед вызовом реализации базового класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

##  <a name="enddialog"></a>CPropertySheet:: EndDialog

Завершает работу страницы свойств.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Параметры

*нендид*<br/>
Идентификатор, который будет использоваться в качестве возвращаемого значения страницы свойств.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается платформой при нажатии кнопки ОК, отмена или закрыть. Вызывайте эту функцию члена, если возникает событие, которое должно закрыть страницу свойств.

Эта функция-член используется только с модальным диалоговым окном.

### <a name="example"></a>Пример

См. пример для [CPropertySheet::P рессбуттон](#pressbutton).

##  <a name="getactiveindex"></a>CPropertySheet:: Жетактивеиндекс

Возвращает номер индекса активной страницы окна свойств, а затем использует возвращенный номер индекса в качестве параметра для `GetPage`.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер индекса активной страницы.

### <a name="example"></a>Пример

См. пример для [CPropertySheet:: жетактивепаже](#getactivepage).

##  <a name="getactivepage"></a>CPropertySheet:: Жетактивепаже

Извлекает активную страницу окна свойств.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на активную страницу.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член для выполнения какого-либо действия на активной странице.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

##  <a name="getpage"></a>CPropertySheet:: @ Page

Возвращает указатель на указанную страницу в этой странице свойств.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>Параметры

*нпаже*<br/>
Индекс нужной страницы, начиная с 0. Значение должно находиться в диапазоне от 0 до числа страниц в таблице свойств включительно.

### <a name="return-value"></a>Возвращаемое значение

Указатель на страницу, соответствующую параметру *нпаже* .

### <a name="example"></a>Пример

См. пример для [CPropertyPage:: онвизардфиниш](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpagecount"></a>CPropertySheet:: Жетпажекаунт

Определяет количество страниц в данный момент на странице свойств.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество страниц в таблице свойств.

### <a name="example"></a>Пример

См. пример для [CPropertyPage:: онвизардфиниш](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpageindex"></a>CPropertySheet:: Жетпажеиндекс

Извлекает номер индекса указанной страницы в таблице свойств.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*ппаже*<br/>
Указывает на страницу с индексом, который необходимо найти. Не может принимать значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Номер индекса страницы.

### <a name="remarks"></a>Примечания

Например, можно использовать `GetPageIndex` для получения индекса страницы, чтобы использовать [сетактивепаже](#setactivepage) или @ [Page](#getpage).

### <a name="example"></a>Пример

См. пример для [CPropertySheet:: жетактивепаже](#getactivepage).

##  <a name="gettabcontrol"></a>CPropertySheet::, TabControl

Извлекает указатель на элемент управления "Вкладка" для выполнения действий, характерных для элемента управления "Вкладка" (то есть для использования любого из API в [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент управления Tab.

### <a name="remarks"></a>Примечания

Например, вызовите эту функцию члена, если необходимо добавить точечные рисунки на каждую из вкладок во время инициализации.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

##  <a name="m_psh"></a>CPropertySheet:: m_psh

Структура, члены которой хранят характеристики [пропшисеадер](/windows/desktop/api/prsht/ns-prsht-propsheetheadera_v2).

### <a name="remarks"></a>Примечания

Используйте эту структуру для инициализации внешнего вида страницы свойств после ее конструирования, но перед отображением с помощью функции-члена [DoModal](#domodal) . Например, установите для `m_psh` элемента *двсизе* в значение размер, который должен иметь страница свойств.

Дополнительные сведения об этой структуре, включая список ее членов, см. в разделе ПРОПШИСЕАДЕР в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

##  <a name="mapdialogrect"></a>CPropertySheet:: Мапдиалогрект

Преобразует единицы диалогового окна прямоугольника в единицы экрана.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*лпрект*<br/>
Указывает на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) , содержащий координаты диалогового окна для преобразования.

### <a name="remarks"></a>Примечания

Единицы диалоговых окон задаются в терминах текущей базовой единицы диалогового окна, производной от средней ширины и высоты символов шрифта, используемого для текста диалогового окна. Одна горизонтальная единица — это одна четвертая единица базовой ширины диалогового окна, а одна единица по вертикали — одна восьмая от базовой единицы высоты диалогового окна.

Функция Windows [жетдиалогбасеунитс](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) возвращает сведения о размере для системного шрифта, но при использовании стиля DS_SETFONT в файле определения ресурса можно указать другой шрифт для каждой страницы свойств. Функция Windows [мапдиалогрект](/windows/desktop/api/winuser/nf-winuser-mapdialogrect) , описанная в Windows SDK, использует соответствующий шрифт для этого диалогового окна.

Функция-член заменяет единицы диалогового окна в лпрект с помощью единиц экрана (пикселей), чтобы прямоугольник можно было использовать для создания диалогового окна или размещения элемента управления в поле. `MapDialogRect`

##  <a name="oninitdialog"></a>CPropertySheet:: Онинитдиалог

Переопределяет для расширения инициализации страницы свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Указывает, было ли приложение установило фокус ввода на один из элементов управления на странице свойств. Если `OnInitDialog` возвращает ненулевое значение, Windows устанавливает фокус ввода на первый элемент управления на странице свойств. Приложение может вернуть значение 0 только в том случае, если оно явно установило фокус ввода на один из элементов управления на странице свойств.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается в ответ на сообщение WM_INITDIALOG. Это сообщение отправляется на вкладку свойств во время вызовов [CREATE](#create) или [DoModal](#domodal) , которые происходят непосредственно перед отображением страницы свойств.

Переопределите эту функцию-член, если необходимо выполнить специальную обработку при инициализации страницы свойств. В переопределенной версии сначала вызовите базовый класс `OnInitDialog` , но не пропустите его возвращаемое значение. Как правило, вы возвращаете значение TRUE из переопределенной функции члена.

Для этой функции-члена не требуется запись схемы сообщений.

##  <a name="pressbutton"></a>CPropertySheet::P Рессбуттон

Имитирует выбранную кнопку на странице свойств.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>Параметры

*нбуттон*<br/>
Нбуттон: Определяет кнопку, которая будет нажата. Этот параметр может принимать одно из следующих значений:

- PSBTN_BACK нажимает кнопку Back (назад).

- PSBTN_NEXT нажимает кнопку Далее.

- PSBTN_FINISH выбирает кнопку Готово.

- PSBTN_OK нажимает кнопку ОК.

- PSBTN_APPLYNOW выбирает кнопку Применить сейчас.

- PSBTN_CANCEL нажимает кнопку Отмена.

- PSBTN_HELP выбирает кнопку "Справка".

### <a name="remarks"></a>Примечания

Дополнительные сведения о сообщении Windows SDK Прессбуттон см. в разделе [PSM_PRESSBUTTON](/windows/desktop/Controls/psm-pressbutton) .

При вызове `PressButton` метода не будет отправлено уведомление [PSN_APPLY](/windows/desktop/Controls/psn-apply) со страницы свойств в платформу. Чтобы отправить это уведомление, вызовите [CPropertyPage:: ОНОК](../../mfc/reference/cpropertypage-class.md#onok).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

##  <a name="removepage"></a>CPropertySheet:: RemovePage

Удаляет страницу из страницы свойств и уничтожает связанное окно.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Параметры

*ппаже*<br/>
Указывает на страницу, которую необходимо удалить из страницы свойств. Не может принимать значение NULL.

*нпаже*<br/>
Индекс страницы, которую необходимо удалить. Значение должно находиться в диапазоне от 0 до числа страниц в таблице свойств включительно.

### <a name="remarks"></a>Примечания

Сам объект [CPropertyPage](../../mfc/reference/cpropertypage-class.md) не уничтожается, пока владелец `CPropertySheet` окна не закроется.

##  <a name="setactivepage"></a>CPropertySheet:: Сетактивепаже

Изменяет активную страницу.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*нпаже*<br/>
Индекс заданной страницы. Значение должно находиться в диапазоне от 0 до числа страниц в таблице свойств включительно.

*ппаже*<br/>
Указывает на страницу, которую необходимо задать в таблице свойств. Он не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если страница свойств активирована успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Например, используйте `SetActivePage` , если действие пользователя на одной странице должно привести к тому, что другая страница станет активной страницей.

### <a name="example"></a>Пример

См. пример для [CPropertySheet:: жетактивепаже](#getactivepage).

##  <a name="setfinishtext"></a>CPropertySheet:: Сетфиништекст

Задает текст для кнопки завершения.

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указывает на текст, который будет отображаться на кнопке Готово.

### <a name="remarks"></a>Примечания

Вызовите `SetFinishText` , чтобы отобразить текст кнопки "Готово" и скрыть кнопки "Далее" и "назад" после того, как пользователь завершит действие на последней странице мастера.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="settitle"></a>CPropertySheet:: Сеттитле

Задает заголовок страницы свойств (текст, отображаемый в заголовке окна фрейма).

```
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>Параметры

*нстиле*<br/>
Задает стиль заголовка страницы свойств. Стиль должен быть указан в 0 или в виде PSH_PROPTITLE. Если стиль задан как PSH_PROPTITLE, после текста, указанного в качестве заголовка, появляется слово «Properties» (свойства). Например, вызов `SetTitle`("Simple", PSH_PROPTITLE) приведет к созданию заголовка страницы свойств "простые свойства".

*lpszText*<br/>
Указывает на текст, который будет использоваться в качестве заголовка в заголовке окна свойств.

### <a name="remarks"></a>Примечания

По умолчанию страница свойств использует параметр Caption в конструкторе страницы свойств.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

##  <a name="setwizardbuttons"></a>CPropertySheet:: Сетвизардбуттонс

Включает или отключает кнопку "назад", "Далее" или "Готово" на странице свойств мастера.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Набор флагов, которые настраивают функцию и внешний вид кнопок мастера. Этот параметр может быть сочетанием следующих значений:

- Кнопка "назад" PSWIZB_BACK

- Кнопка "PSWIZB_NEXT" Далее

- Кнопка завершения PSWIZB_FINISH

- Кнопка завершения "PSWIZB_DISABLEDFINISH Disabled"

### <a name="remarks"></a>Примечания

Вызывайте `SetWizardButtons` только после открытия диалогового окна; невозможно вызвать `SetWizardButtons` метод перед вызовом [DoModal](#domodal). Как правило, следует вызывать `SetWizardButtons` из [CPropertyPage:: онсетактиве](../../mfc/reference/cpropertypage-class.md#onsetactive).

Если необходимо изменить текст кнопки Готово или скрыть кнопки Далее и назад после завершения работы мастера пользователем, вызовите [сетфиништекст](#setfinishtext). Обратите внимание, что одна и та же кнопка является общей для Finish и Next. Можно одновременно отобразить кнопку "Готово" или "Далее".

### <a name="example"></a>Пример

У есть три страницы свойств мастера: `CStylePage`, `CColorPage`и `CShapePage`. `CPropertySheet`  В следующем фрагменте кода показано, как включить и отключить кнопки " **назад** " и " **Далее** " на странице свойств мастера.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="setwizardmode"></a>CPropertySheet:: Сетвизардмоде

Устанавливает страницу свойств в качестве мастера.

```
void SetWizardMode();
```

### <a name="remarks"></a>Примечания

Ключевой характеристикой страницы свойств мастера является то, что пользователь переходит с помощью кнопок «Далее» или «Готово», «назад» и «Отмена» вместо вкладок.

Вызовите метод `SetWizardMode` перед вызовом [DoModal](#domodal). После вызова метод `SetWizardMode` `DoModal` возвратит значение ID_WIZFINISH (если пользователь закрывается с помощью кнопки Готово) или идканцел.

`SetWizardMode`задает флаг PSH_WIZARD.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>См. также

[Пример CMNCTRL1 для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример CMNCTRL2 для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример ПРОПДЛГ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
