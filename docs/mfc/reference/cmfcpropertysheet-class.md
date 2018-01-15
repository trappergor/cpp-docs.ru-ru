---
title: "Класс CMFCPropertySheet | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2684de5c72dcc755c2a75e2553eed509ce76533
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpropertysheet-class"></a>Класс CMFCPropertySheet
Класс `CMFCPropertySheet` поддерживает таблицу свойств, каждая страница свойств в которой обозначается вкладкой, кнопкой панели инструментов, узлом элемента управления «Дерево» или элементом списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Создает объект `CMFCPropertySheet`.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPropertySheet::AddPage](#addpage)|Добавляет страницу в таблицу свойств.|  
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Добавляет новую страницу свойств в элемент управления «Дерево».|  
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Добавляет новый узел в элемент управления «Дерево».|  
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.|  
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Получает высоту текущего заголовка.|  
|[CMFCPropertySheet::GetLook](#getlook)|Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.|  
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Получает ширину панели навигации в пикселях.|  
|[CMFCPropertySheet::GetTab](#gettab)|Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».|  
|`CMFCPropertySheet::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Инициализирует появление текущего элемента управления «Страница свойств».|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Вызывается платформой при включении страницы свойств.|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Вызывается платформой для отрисовки пользовательского заголовка страницы свойств.|  
|`CMFCPropertySheet::OnInitDialog`|Обрабатывает [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщения. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».|  
|`CMFCPropertySheet::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет `CPropertySheet::PreTranslateMessage`.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Удаляет узел из элемента управления «Дерево».|  
|[CMFCPropertySheet::RemovePage](#removepage)|Удаляет страницу свойств из таблицы свойств.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Указывает список изображений, используемых в элементе управления навигации панели Outlook.|  
|[CMFCPropertySheet::SetLook](#setlook)|Задает внешний вид таблицы свойств.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CMFCPropertySheet` представляет таблицы свойств, также называемые диалоговыми окнами с вкладками. Класс `CMFCPropertySheet` может отображать страницу свойств различными способами.  
  
 Чтобы использовать класс `CMFCPropertySheet` в приложении, выполните следующие действия.  
  
1.  Создайте класс из класса `CMFCPropertySheet` и дайте ему имя, например CMyPropertySheet.  
  
2.  Создать [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) объект для каждой страницы свойств.  
  
3.  Вызовите [CMFCPropertySheet::SetLook](#setlook) метод в конструкторе cmypropertysheet. Параметр этого метода указывает, что страницы свойств должны отображаться как вкладки вдоль верхней или левой стороны таблицы свойств, как вкладки в стиле таблицы свойств Microsoft OneNote свойств, как кнопки в элементе управления «Панель инструментов» Microsoft Outlook, как узлы дерева или как список элементов с левой стороны таблицы свойств.  
  
4.  При создании свойств в стиле панели инструментов Microsoft Outlook, вызовите [CMFCPropertySheet::SetIconsList](#seticonslist) способ связывания списка изображений со страницами свойств.  
  
5.  Вызовите [CMFCPropertySheet::AddPage](#addpage) метод для каждой страницы свойств.  
  
6.  Создайте элемент управления `CMFCPropertySheet` и вызовите его метод `DoModal`.  
  
## <a name="illustrations"></a>Рисунки  
 На следующем рисунке показана таблица свойств в стиле встроенной панели инструментов Microsoft Outlook. Панель инструментов Outlook отображается с левой стороны таблицы свойств.  
  
 ![Элементы управления цветов CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet_color")  
  
 На следующем рисунке показана страница свойств, который содержит [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) объекта. Этот объект является таблицей свойств в стиле стандартной страницы свойств общих элементов управления.  
  
 ![Элементы управления свойств и списков CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet_list")  
  
 На следующем рисунке показана таблица свойств в стиле элемента управления «Дерево».  
  
 ![Дерево свойства](../../mfc/reference/media/proptree.png "proptree")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertysheet.h  
  
##  <a name="addpage"></a>CMFCPropertySheet::AddPage  
 Добавляет страницу в таблицу свойств.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPage`  
 Указатель на объект страницы. Этот параметр не может быть `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет страницу указанное свойство как правых вкладки в окне свойств. Таким образом используйте этот метод для добавления страниц в порядке слева направо.  
  
 Если окно свойств в стиле Microsoft Outlook, платформа отображает список кнопок навигации в левой части страницы свойств. После этого метод добавляет страницу свойств, соответствующая кнопка добавляет в список. Для отображения страницы свойств, щелкните соответствующую ему кнопку. Дополнительные сведения о стилях вкладок свойств, см. в разделе [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="addpagetotree"></a>CMFCPropertySheet::AddPageToTree  
 Добавляет новую страницу свойств в элемент управления «Дерево».  
  
```  
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,  
    CMFCPropertyPage* pPage,  
    int nIconNum=-1,  
    int nSelIconNum=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCategory`  
 Указатель на родительский узел дерева или `NULL` связываемый указанную страницу с узел верхнего уровня. Вызовите [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод, чтобы получить этот указатель.  
  
 [in] `pPage`  
 Указатель на объект страницы свойств.  
  
 [in] `nIconNum`  
 Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом со страницы свойств элемента управления дерева, когда страница не выбран. Значение по умолчанию — -1.  
  
 [in] `nSelIconNum`  
 Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом со страницы свойств элемента управления дерева при выборе страницы. Значение по умолчанию — -1.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет страницу свойств в качестве конечного элемента управления дерева. Добавление страницы свойств, создания `CMFCPropertySheet` , вызовите [CMFCPropertySheet::SetLook](#setlook) метод с `look` равным `CMFCPropertySheet::PropSheetLook_Tree`и затем использовать этот метод для добавления на странице свойств.  
  
##  <a name="addtreecategory"></a>CMFCPropertySheet::AddTreeCategory  
 Добавляет новый узел в элемент управления «Дерево».  
  
```  
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,  
    int nIconNum=-1,  
    int nSelectedIconNum=-1,  
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Имя узла.  
  
 [in] `nIconNum`  
 Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом со страницы свойств элемента управления дерева, когда страница не выбран. Значение по умолчанию — -1.  
  
 [in] `nSelectedIconNum`  
 Отсчитываемый от нуля индекс значка или -1, если значок не используется. Значок отображается рядом со страницы свойств элемента управления дерева при выборе страницы. Значение по умолчанию — -1.  
  
 [in] `pParentCategory`  
 Указатель на родительский узел дерева или `NULL` связываемый указанную страницу с узел верхнего уровня. Установите этот параметр с [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый узел в элементе управления иерархического представления.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для добавления нового узла, которую также называют категорию, в элементе управления иерархического представления. Чтобы добавить узел, создайте `CMFCPropertySheet` , вызовите [CMFCPropertySheet::SetLook](#setlook) метод с `look` равным `CMFCPropertySheet::PropSheetLook_Tree`и этот метод используется для добавления узла.  
  
 Использовать возвращаемое значение этого метода в последующих вызовах [CMFCPropertySheet::AddPageToTree](#addpagetotree) и [CMFCPropertySheet::AddTreeCategory](#addtreecategory).  
  
##  <a name="cmfcpropertysheet"></a>CMFCPropertySheet::CMFCPropertySheet  
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
 [in] `pszCaption`  
 Строка, содержащая заголовок листа свойств. Не может быть `NULL`.  
  
 [in] `nIDCaption`  
 Идентификатор ресурса, содержащее заголовок листа свойств.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно страницы свойств, или `NULL` если родительское окно является главным окном приложения. Значение по умолчанию — `NULL`.  
  
 [in] `iSelectPage`  
 Отсчитываемый от нуля индекс страницы свойств top. Значение по умолчанию — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе параметров для [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) конструктор.  
  
##  <a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader  
 Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHeaderHeight`  
 Высота заголовка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Чтобы использовать значение `nHeaderHeight` переопределить параметр для отрисовки пользовательского заголовка [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) метод.  
  
##  <a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight  
 Получает высоту текущего заголовка.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота заголовка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метод перед вызовом этого метода.  
  
##  <a name="getlook"></a>CMFCPropertySheet::GetLook  
 Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из значений перечисления, которое определяет внешний вид таблицы свойств. Список возможных значений, см. в таблице перечисления в подразделе "Примечания" [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="getnavbarwidth"></a>CMFCPropertySheet::GetNavBarWidth  
 Получает ширину панели навигации.  
  
```  
int GetNavBarWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина панели навигации в пикселях.  
  
##  <a name="gettab"></a>CMFCPropertySheet::GetTab  
 Получает внутренний объект набора вкладок, который поддерживает текущий элемент управления «Страница свойств».  
  
```  
CMFCTabCtrl& GetTab() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект внутреннего набора вкладок.  
  
### <a name="remarks"></a>Примечания  
 Окно свойств можно задать, чтобы он отображался в различных стилей, таких как дерево, список кнопки навигации или набора страниц с вкладками.  
  
 Перед вызовом этого метода необходимо вызвать [CMFCPropertySheet::SetLook](#setlook) метод, чтобы задать внешний вид элемента управления листа свойств. Затем вызовите [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) метод, чтобы инициализировать объект внутреннего набора вкладок. Используйте этот метод для извлечения объекта элемента управления tab, а затем использовать этот объект для работы с вкладками на странице свойств.  
  
 Этот метод подтверждает в режиме отладки, если управления лист свойств не задано отображение в стиле Microsoft OneNote.  
  
##  <a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl  
 Инициализирует появление текущего элемента управления «Страница свойств».  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно элемента управления страниц свойств.  
  
### <a name="remarks"></a>Примечания  
 Элемента управления на лист свойств могут отображаться в нескольких различных форм, таких как набор страниц с вкладками, дерево или список кнопок навигации. Используйте [CMFCPropertySheet::SetLook](#setlook) метод, чтобы задать внешний вид элемента управления листа свойств.  
  
##  <a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage  
 Вызывается платформой при включении страницы свойств.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPage`  
 Указатель на объект страницы свойства, представляющее страницу свойств enabled.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод гарантирует, что для свойства enabled страницы в области просмотра. Если стиль текущей таблицы свойств содержит область Microsoft Outlook, этот метод задает соответствующей кнопки Outlook в установленном состоянии.  
  
##  <a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader  
 Вызывается платформой для отрисовки в заголовке страницы пользовательских свойств.  
  
```  
virtual void OnDrawPageHeader(
    CDC* pDC,  
    int nPage,  
    CRect rectHeader);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `nPage`  
 Номер страницы свойств (с нуля).  
  
 [in] `rectHeader`  
 Ограничивающий прямоугольник, указывающий, куда для отрисовки заголовка.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. При переопределении этого метода следует вызвать [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метод перед платформа вызывает этот метод.  
  
##  <a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage  
 Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPage`  
 Указатель на объект page свойство, представляющее страницу свойств для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="removecategory"></a>CMFCPropertySheet::RemoveCategory  
 Удаляет узел из элемента управления «Дерево».  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCategory`  
 Указатель на категорию (узел) для удаления.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы удалить узел, который также называется категорию, из элемента управления дерева. Используйте [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод, чтобы добавить узел в структуре дерева.  
  
##  <a name="removepage"></a>CMFCPropertySheet::RemovePage  
 Удаляет страницу свойств из таблицы свойств.  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPage`  
 Указатель на объект страницы свойство, представляющее страницу свойств для удаления. Не может быть `NULL`.  
  
 [in] `nPage`  
 Отсчитываемый от нуля индекс страницы для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет указанное свойство страницы и уничтожает его соответствующее окно. На странице свойств объекта, `pPage` указывает не уничтожается, пока не [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) закрытия окна.  
  
##  <a name="seticonslist"></a>CMFCPropertySheet::SetIconsList  
 Указывает список изображений, используемых в элементе управления навигации панели Outlook.  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiImageListResID`  
 Идентификатор ресурса для списка изображений.  
  
 [in] `cx`  
 Ширина в пикселях значки в списке изображений.  
  
 [in] `clrTransparent`  
 Цвет прозрачное изображение. Части изображения, которые имеют этот цвет будет прозрачной. Значение по умолчанию — пурпурный цвет RGB(255,0,255).  
  
 [in] `hIcons`  
 Дескриптор существующего списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Во-первых, перегрузки синтаксис, `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если окно свойств в стиле Microsoft Outlook, платформа отображает список кнопок навигации-элемент управления панели Outlook, в левой части страницы свойств. Используйте этот метод, чтобы задать список изображений для использования элементом управления панели Outlook.  
  
 Дополнительные сведения о методах, которые поддерживают этот метод см. в разделе [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) и [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Дополнительные сведения о том, как задать стиль таблицы свойств см. в разделе [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="setlook"></a>CMFCPropertySheet::SetLook  
 Задает внешний вид таблицы свойств.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `look`  
 Одно из значений перечисления, которое определяет внешний вид таблицы свойств. Стиль по умолчанию для страницы свойств- `CMFCPropertySheet::PropSheetLook_Tabs`. Дополнительные сведения см. в таблице в подразделе «Примечания».  
  
 [in] `nNavControlWidth`  
 Ширина элемента навигации в пикселях. Значение по умолчанию — 100.  
  
### <a name="remarks"></a>Примечания  
 Чтобы отобразить окно свойств в стиль, используемый по умолчанию, этот метод перед тем как создать окно страницы свойств.  
  
 В следующей таблице перечислены значений перечисления, которые могут быть указаны в `look` параметра.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(По умолчанию) Отображает вкладку для каждой страницы свойств. Вкладки отображаются в верхней части страницы свойств и помещаются в стек, если имеется больше вкладок, чем может поместиться на одной строке.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Отображает список кнопок навигации в стиле панели Microsoft Outlook в левой части страницы свойств. Каждая кнопка в списке соответствует странице свойств. Если доступны дополнительные кнопки, чем может поместиться в видимой области списка, платформа отображает стрелок прокрутки.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|Отображает элемент управления дерева в левой части страницы свойств. Каждый родительский или дочерний узел элемента управления дерева соответствует странице свойств. Платформа отображает стрелок прокрутки, если больше узлов, чем помещается в видимую область элемента управления дерева.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Отображает вкладку, в стиле Microsoft OneNote для каждой страницы свойств. Платформа отображает вкладки в верхней части страницы свойств и кнопок прокрутки при наличии нескольких вкладок, чем помещается в одной строке.|  
|`CMFCPropertySheet::PropSheetLook_List`|Отображает список в левой части страницы свойств. Соответствует странице свойств каждого элемента списка. Если не все элементы списка, чем помещается в видимую область списка, платформа отображает стрелками.|  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)
