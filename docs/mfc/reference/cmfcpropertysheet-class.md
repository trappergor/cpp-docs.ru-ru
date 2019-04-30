---
title: Класс CMFCPropertySheet
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: 7e5b553e6a10bee0e5b05bb32b9af3069269ca91
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344225"
---
# <a name="cmfcpropertysheet-class"></a>Класс CMFCPropertySheet

Класс `CMFCPropertySheet` поддерживает таблицу свойств, каждая страница свойств в которой обозначается вкладкой, кнопкой панели инструментов, узлом элемента управления «Дерево» или элементом списка.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Создает объект `CMFCPropertySheet`.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|Добавляет страницу в таблицу свойств.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Добавляет новую страницу свойств в элемент управления «Дерево».|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Добавляет новый узел в элемент управления «Дерево».|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Получает высоту текущего заголовка.|
|[CMFCPropertySheet::GetLook](#getlook)|Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Получает ширину панели навигации в пикселях.|
|[CMFCPropertySheet::GetTab](#gettab)|Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».|
|`CMFCPropertySheet::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Инициализирует появление текущего элемента управления «Страница свойств».|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Вызывается платформой при включении страницы свойств.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Вызывается платформой для отрисовки пользовательского заголовка страницы свойств.|
|`CMFCPropertySheet::OnInitDialog`|Обрабатывает [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) сообщения. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».|
|`CMFCPropertySheet::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) функции Windows. (Переопределяет `CPropertySheet::PreTranslateMessage`.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Удаляет узел из элемента управления «Дерево».|
|[CMFCPropertySheet::RemovePage](#removepage)|Удаляет страницу свойств из таблицы свойств.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Указывает список изображений, используемых в элементе управления навигации панели Outlook.|
|[CMFCPropertySheet::SetLook](#setlook)|Задает внешний вид таблицы свойств.|

## <a name="remarks"></a>Примечания

Класс `CMFCPropertySheet` представляет таблицы свойств, также называемые диалоговыми окнами с вкладками. Класс `CMFCPropertySheet` может отображать страницу свойств различными способами.

Чтобы использовать класс `CMFCPropertySheet` в приложении, выполните следующие действия.

1. Создайте класс из класса `CMFCPropertySheet` и дайте ему имя, например CMyPropertySheet.

1. Создать [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) объект для каждой страницы свойств.

1. Вызовите [CMFCPropertySheet::SetLook](#setlook) метод в конструкторе cmypropertysheet. Параметр этого метода указывает, что страницы свойств должны отображаться как вкладки вдоль верхней или левой стороны таблицы свойств, как вкладки в стиле таблицы свойств Microsoft OneNote свойств, как кнопки в элементе управления «Панель инструментов» Microsoft Outlook, как узлы дерева или как список элементов с левой стороны таблицы свойств.

1. Если вы создаете таблицу свойств в стиле панели инструментов Microsoft Outlook, вызовите [CMFCPropertySheet::SetIconsList](#seticonslist) способ связывания списка изображений со страницами свойств.

1. Вызовите [CMFCPropertySheet::AddPage](#addpage) метод для каждой страницы свойств.

1. Создайте элемент управления `CMFCPropertySheet` и вызовите его метод `DoModal`.

## <a name="illustrations"></a>Рисунки

На следующем рисунке показана таблица свойств в стиле встроенной панели инструментов Microsoft Outlook. Панель инструментов Outlook отображается с левой стороны таблицы свойств.

![Элементы управления цветов CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "элементы управления цветов CMFCPropertySheet")

На следующем рисунке показана таблица свойств содержит [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) объекта. Этот объект является таблицей свойств в стиле стандартной страницы свойств общих элементов управления.

![Элементы управления свойств и списков CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "управления свойств и списков CMFCPropertySheet")

На следующем рисунке показана таблица свойств в стиле элемента управления «Дерево».

![Свойство дерева](../../mfc/reference/media/proptree.png "дерева свойства")

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertysheet.h

##  <a name="addpage"></a>  CMFCPropertySheet::AddPage

Добавляет страницу в таблицу свойств.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
[in] Указатель на объект страницы. Этот параметр не может иметь значение NULL.

### <a name="remarks"></a>Примечания

Этот метод добавляет указанное свойство страницы как крайняя вкладка в окне свойств. Таким образом этот метод можно используйте, чтобы добавить страницы в порядке слева направо.

Если окно свойств в стиле Microsoft Outlook, платформа отображает список кнопок навигации в левой части страницы свойств. После этого метод добавляет страницу свойств, он добавляет соответствующую кнопку в список. Чтобы отобразить страницу свойств, щелкните его соответствующую кнопку. Дополнительные сведения о стилях страниц свойств, см. в разделе [CMFCPropertySheet::SetLook](#setlook).

##  <a name="addpagetotree"></a>  CMFCPropertySheet::AddPageToTree

Добавляет новую страницу свойств в элемент управления «Дерево».

```
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>Параметры

*pCategory*<br/>
[in] Указатель на родительский узел дерева, или значение NULL, должен быть сопоставлен указанную страницу узел верхнего уровня. Вызовите [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод, чтобы получить этот указатель.

*Физ_страница*<br/>
[in] Указатель на объект страницы свойств.

*nIconNum*<br/>
[in] Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом с страницу свойств элемента управления дерева, если страницы не выбран. Значение по умолчанию — -1.

*nSelIconNum*<br/>
[in] Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом со страницей свойств элемента управления дерева, при выборе страницы. Значение по умолчанию — -1.

### <a name="remarks"></a>Примечания

Этот метод добавляет страницу свойств в качестве конечного элемента управления дерева. Чтобы добавить страницы свойств, создайте `CMFCPropertySheet` , вызовите [CMFCPropertySheet::SetLook](#setlook) метод с *выглядеть* параметру присвоить `CMFCPropertySheet::PropSheetLook_Tree`и затем использовать этот метод для добавления на страницу свойств .

##  <a name="addtreecategory"></a>  CMFCPropertySheet::AddTreeCategory

Добавляет новый узел в элемент управления «Дерево».

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Имя узла.

*nIconNum*<br/>
[in] Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом с страницу свойств элемента управления дерева, если страницы не выбран. Значение по умолчанию — -1.

*nSelectedIconNum*<br/>
[in] Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом со страницей свойств элемента управления дерева, при выборе страницы. Значение по умолчанию — -1.

*pParentCategory*<br/>
[in] Указатель на родительский узел дерева, или значение NULL, должен быть сопоставлен указанную страницу узел верхнего уровня. Установите этот параметр с [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый узел в структуре дерева.

### <a name="remarks"></a>Примечания

Этот метод позволяет добавить новый узел, который также называется категорию, элементу управления иерархического. Чтобы добавить узел, создайте `CMFCPropertySheet` , вызовите [CMFCPropertySheet::SetLook](#setlook) метод с *выглядеть* параметру присвоить `CMFCPropertySheet::PropSheetLook_Tree`и затем использовать этот метод для добавления узла.

Используйте возвращаемое значение этого метода в последующих вызовах [CMFCPropertySheet::AddPageToTree](#addpagetotree) и [CMFCPropertySheet::AddTreeCategory](#addtreecategory).

##  <a name="cmfcpropertysheet"></a>  CMFCPropertySheet::CMFCPropertySheet

Создает объект `CMFCPropertySheet`.

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>Параметры

*pszCaption*<br/>
[in] Строка, содержащая заголовок листа свойств. Не может принимать значение NULL.

*nIDCaption*<br/>
[in] Идентификатор ресурса, содержащее заголовок листа свойств.

*pParentWnd*<br/>
[in] Указатель на родительское окно свойств, или значение NULL, если родительское окно главное окно приложения. Значение по умолчанию имеет значение NULL.

*iSelectPage*<br/>
[in] Отсчитываемый от нуля индекс страницы свойство top. Значение по умолчанию — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в параметрах [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) конструктор.

##  <a name="enablepageheader"></a>  CMFCPropertySheet::EnablePageHeader

Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Параметры

*nHeaderHeight*<br/>
[in] Высота заголовка в пикселях.

### <a name="remarks"></a>Примечания

Чтобы использовать значение *nHeaderHeight* переопределить параметр для отрисовки пользовательского заголовка, [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) метод.

##  <a name="getheaderheight"></a>  CMFCPropertySheet::GetHeaderHeight

Получает высоту текущего заголовка.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Высота заголовка в пикселях.

### <a name="remarks"></a>Примечания

Вызовите [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метод перед вызовом этого метода.

##  <a name="getlook"></a>  CMFCPropertySheet::GetLook

Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления, указывающее внешний вид страницы свойств. Список возможных значений см. в таблице перечисления в разделе "Примечания" [CMFCPropertySheet::SetLook](#setlook).

##  <a name="getnavbarwidth"></a>  CMFCPropertySheet::GetNavBarWidth

Получает ширину панели навигации.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина панели навигации в пикселях.

##  <a name="gettab"></a>  CMFCPropertySheet::GetTab

Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект внутреннего набора вкладок.

### <a name="remarks"></a>Примечания

Страницы свойств можно задать, чтобы он отображался в различных стилей, таких как дерево, список кнопок навигации или набор страниц с вкладками.

Перед вызовом этого метода вызовите [CMFCPropertySheet::SetLook](#setlook) метод, чтобы задать внешний вид элемента управления таблицы свойств. Затем вызовите [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) метод для инициализации объект внутреннего набора вкладок. Этот метод позволяет получить объект набора вкладок и затем использовать этот объект для работы с вкладками на странице свойств.

Этот метод утверждения в режиме отладки, если управления страниц свойств не задано отображение в стиле Microsoft OneNote.

##  <a name="initnavigationcontrol"></a>  CMFCPropertySheet::InitNavigationControl

Инициализирует появление текущего элемента управления «Страница свойств».

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно элемента управления страниц свойств.

### <a name="remarks"></a>Примечания

Элемент управления свойство таблицы стилей могут отображаться в несколько различных форм, таких как набор страниц с вкладками, дерево или список кнопок навигации. Используйте [CMFCPropertySheet::SetLook](#setlook) метод, чтобы задать внешний вид элемента управления таблицы свойств.

##  <a name="onactivatepage"></a>  CMFCPropertySheet::OnActivatePage

Вызывается платформой при включении страницы свойств.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
[in] Указатель на объект page свойство, представляющее страницу свойств enabled.

### <a name="remarks"></a>Примечания

По умолчанию этот метод гарантирует, что свойство enabled страницы в области просмотра. Если стиль текущей таблицы свойств содержит область Microsoft Outlook, этот метод задает соответствующую кнопку Outlook в состоянии установленного флажка.

##  <a name="ondrawpageheader"></a>  CMFCPropertySheet::OnDrawPageHeader

Вызывается платформой для отрисовки заголовка для страницы пользовательских свойств.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

*nPage*<br/>
[in] Номер страницы свойств (с нуля).

*rectHeader*<br/>
[in] Ограничивающий прямоугольник, который указывает, где для рисования заголовка.

### <a name="remarks"></a>Примечания

По умолчанию этот метод не выполняет никаких действий. При переопределении этого метода, вызвать [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метод, прежде чем платформа вызывает этот метод.

##  <a name="onremovetreepage"></a>  CMFCPropertySheet::OnRemoveTreePage

Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
[in] Указатель на объект page свойство, представляющее страницу свойств для удаления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

##  <a name="removecategory"></a>  CMFCPropertySheet::RemoveCategory

Удаляет узел из элемента управления «Дерево».

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Параметры

*pCategory*<br/>
[in] Указатель на категорию (узел), чтобы удалить.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы удалить узел, который также называется категорию, из элемента управления дерева. Используйте [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод для добавления узла в дерево.

##  <a name="removepage"></a>  CMFCPropertySheet::RemovePage

Удаляет страницу свойств из таблицы свойств.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Параметры

*Физ_страница*<br/>
[in] Указатель на объект страницы свойство, представляющее страницу свойств для удаления. Не может принимать значение NULL.

*nPage*<br/>
[in] Отсчитываемый от нуля индекс, которую требуется удалить.

### <a name="remarks"></a>Примечания

Этот метод удаляет указанное свойство страницу и уничтожает в соответствующем окне. На странице свойств объекта, *Физ_страница* параметр указывает, не уничтожается, пока не [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) окно закрыто.

##  <a name="seticonslist"></a>  CMFCPropertySheet::SetIconsList

Указывает список изображений, используемых в элементе управления навигации панели Outlook.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>Параметры

*uiImageListResID*<br/>
[in] Идентификатор ресурса из списка изображений.

*cx*<br/>
[in] Ширина в пикселях значки в списке изображений.

*clrTransparent*<br/>
[in] Цвет прозрачное изображение. Части изображения, которые имеют этот цвет будет прозрачным. Значение по умолчанию — пурпурный цвет RGB(255,0,255).

*объектами HICON*<br/>
[in] Дескриптор существующего списка изображений.

### <a name="return-value"></a>Возвращаемое значение

Первый способ заключается в перегружать синтаксис, значение TRUE в случае успешного выполнения; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если окно свойств в стиле Microsoft Outlook, платформа отображает список кнопок навигации-элемент управления панели Outlook, в левой части страницы свойств. Этот метод позволяет задать список изображений для использования элементом управления панели Outlook.

Дополнительные сведения о методах, которые поддерживают этот метод, см. в разделе [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) и [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Дополнительные сведения о том, как задать стиль свойств см. в разделе [CMFCPropertySheet::SetLook](#setlook).

##  <a name="setlook"></a>  CMFCPropertySheet::SetLook

Задает внешний вид таблицы свойств.

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Параметры

*внешний вид*<br/>
[in] Одно из значений перечисления, указывающее внешний вид страницы свойств. Стиль по умолчанию для страницы свойств является `CMFCPropertySheet::PropSheetLook_Tabs`. Дополнительные сведения см. в таблице в разделе "Примечания" в этом разделе.

*nNavControlWidth*<br/>
[in] Ширина элемента навигации в пикселях. Значение по умолчанию — 100.

### <a name="remarks"></a>Примечания

Чтобы отобразить страницу свойств в стиле кроме порта по умолчанию, этот метод перед созданием окна таблицы свойств.

В следующей таблице перечислены значения перечисления, которые могут быть указаны в *выглядеть* параметра.

|Значение|Описание|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(По умолчанию) Отображает вкладки для каждой страницы свойств. Вкладки отображаются в верхней части страницы свойств и помещаются в стек, если есть несколько вкладок, чем может поместиться в одну строку.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Отображает список кнопок навигации в стиле Microsoft Outlook линейки с левой стороны страницы свойств. Каждой кнопке в списке соответствует страницы свойств. Если доступны дополнительные кнопки, чем может поместиться в видимой части списка, платформа отображает стрелки прокрутки.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Отображает элемент управления дерева в левой части страницы свойств. Каждый родительский или дочерний узел элемента управления дерева соответствует страницы свойств. Если больше узлов, чем может поместиться в видимой области элемента управления дерева, платформа отображает стрелки прокрутки.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Отображает вкладку, в стиле Microsoft OneNote для каждой страницы свойств. Платформа отображает вкладки в верхней части страницы свойств и стрелками Если есть несколько вкладок, чем может поместиться в одну строку.|
|`CMFCPropertySheet::PropSheetLook_List`|Отображение списка с левой стороны страницы свойств. Каждый элемент списка соответствует страницы свойств. Если не все элементы списка, чем может поместиться в видимой части списка, платформа отображает стрелки прокрутки.|

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)
