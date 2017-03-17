---
title: "Класс CMFCPropertySheet | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertySheet::PreTranslateMessage method
- CMFCPropertySheet::OnInitDialog method
- CMFCPropertySheet class
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
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
ms.openlocfilehash: a157a0afa4542bc023ba4d7149e78a71bbd56e74
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertysheet-class"></a>Класс CMFCPropertySheet
Класс `CMFCPropertySheet` поддерживает таблицу свойств, каждая страница свойств в которой обозначается вкладкой, кнопкой панели инструментов, узлом элемента управления «Дерево» или элементом списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Создает объект `CMFCPropertySheet`.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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
|`CMFCPropertySheet::OnInitDialog`|Обрабатывает [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) сообщение. (Переопределяет [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».|  
|`CMFCPropertySheet::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет `CPropertySheet::PreTranslateMessage`.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Удаляет узел из элемента управления «Дерево».|  
|[CMFCPropertySheet::RemovePage](#removepage)|Удаляет страницу свойств из таблицы свойств.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Указывает список изображений, используемых в элементе управления навигации панели Outlook.|  
|[CMFCPropertySheet::SetLook](#setlook)|Задает внешний вид таблицы свойств.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CMFCPropertySheet` представляет таблицы свойств, также называемые диалоговыми окнами с вкладками. Класс `CMFCPropertySheet` может отображать страницу свойств различными способами.  
  
 Чтобы использовать класс `CMFCPropertySheet` в приложении, выполните следующие действия.  
  
1.  Создайте класс из класса `CMFCPropertySheet` и дайте ему имя, например CMyPropertySheet.  
  
2.  Создать [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) объект для каждой страницы свойств.  
  
3.  Вызов [CMFCPropertySheet::SetLook](#setlook) в конструкторе CMyPropertySheet. Параметр этого метода указывает, что страницы свойств должны отображаться как вкладки вдоль верхней или левой стороны таблицы свойств, как вкладки в стиле таблицы свойств Microsoft OneNote свойств, как кнопки в элементе управления «Панель инструментов» Microsoft Outlook, как узлы дерева или как список элементов с левой стороны таблицы свойств.  
  
4.  При создании страницы свойств в стиле Microsoft Outlook панели инструментов вызвать [CMFCPropertySheet::SetIconsList](#seticonslist) способ связывания списка изображений вместе со страницы свойств.  
  
5.  Вызов [CMFCPropertySheet::AddPage](#addpage) метод для каждой страницы свойств.  
  
6.  Создайте элемент управления `CMFCPropertySheet` и вызовите его метод `DoModal`.  
  
## <a name="illustrations"></a>Рисунки  
 На следующем рисунке показана таблица свойств в стиле встроенной панели инструментов Microsoft Outlook. Панель инструментов Outlook отображается с левой стороны таблицы свойств.  
  
 ![Элементы управления цветов CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet_color")  
  
 На следующем рисунке показано окно свойств, который содержит [CMFCPropertyGridCtrl класс](../../mfc/reference/cmfcpropertygridctrl-class.md) объекта. Этот объект является таблицей свойств в стиле стандартной страницы свойств общих элементов управления.  
  
 ![Элементы управления свойств и списков CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet_list")  
  
 На следующем рисунке показана таблица свойств в стиле элемента управления «Дерево».  
  
 ![Дерево](../../mfc/reference/media/proptree.png "proptree")  
  
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
 Этот метод добавляет страницу указанное свойство как правое вкладки в окне свойств. Таким образом используйте этот метод для добавления страниц в порядке слева направо.  
  
 Если окно свойств в стиле Microsoft Outlook, платформа список кнопок навигации в левом окне свойств. После того, этот метод добавляет страницу свойств, соответствующая кнопка добавляет в список. Для отображения страницы свойств, щелкните соответствующую ему кнопку. Дополнительные сведения о стилях свойств см. в разделе [CMFCPropertySheet::SetLook](#setlook).  
  
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
 Указатель на родительский узел дерева или `NULL` связываемый указанную страницу с узла верхнего уровня. Вызов [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод, чтобы получить этот указатель.  
  
 [in] `pPage`  
 Указатель на объект страницы свойств.  
  
 [in] `nIconNum`  
 Отсчитываемый от нуля индекс значка или значение -1, если значок не используется. Значок отображается рядом со страницы свойств управления дерева при страницы не выбран. Значение по умолчанию — -1.  
  
 [in] `nSelIconNum`  
 Отсчитываемый от нуля индекс значка или значение -1, если значок не используется. Значок отображается рядом со страницы свойств управления дерева при выборе страницы. Значение по умолчанию — -1.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет страницу свойств в качестве конечного элемента управления дерева. Чтобы добавить страницу свойств, создайте `CMFCPropertySheet` , вызовите [CMFCPropertySheet::SetLook](#setlook) метода с `look` параметра `CMFCPropertySheet::PropSheetLook_Tree`и затем использовать этот метод для добавления на странице свойств.  
  
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
 Отсчитываемый от нуля индекс значка или значение -1, если значок не используется. Значок отображается рядом со страницы свойств управления дерева при страницы не выбран. Значение по умолчанию — -1.  
  
 [in] `nSelectedIconNum`  
 Отсчитываемый от нуля индекс значка или значение -1, если значок не используется. Значок отображается рядом со страницы свойств управления дерева при выборе страницы. Значение по умолчанию — -1.  
  
 [in] `pParentCategory`  
 Указатель на родительский узел дерева или `NULL` связываемый указанную страницу с узла верхнего уровня. Задайте этот параметр с [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый узел в структуре дерева.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы добавить новый узел, который также называют категорию, элементу управления иерархического. Чтобы добавить узел, создать `CMFCPropertySheet` , вызовите [CMFCPropertySheet::SetLook](#setlook) метод `look` параметра `CMFCPropertySheet::PropSheetLook_Tree`и затем использовать этот метод для добавления узла.  
  
 С помощью возвращаемого значения этого метода в последующих вызовах [CMFCPropertySheet::AddPageToTree](#addpagetotree) и [CMFCPropertySheet::AddTreeCategory](#addtreecategory).  
  
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
 Отсчитываемый от нуля индекс страницу основных свойств. Значение по умолчанию — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе параметры для [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) конструктор.  
  
##  <a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader  
 Резервирует место в верхней части каждой страницы для отрисовки пользовательского заголовка.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHeaderHeight`  
 Высота заголовка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Чтобы использовать значение `nHeaderHeight` переопределить параметр для рисования пользовательского заголовка [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) метод.  
  
##  <a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight  
 Получает высоту текущего заголовка.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота заголовка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызов [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метода перед вызовом этого метода.  
  
##  <a name="getlook"></a>CMFCPropertySheet::GetLook  
 Получает значение перечисления, указывающее внешний вид текущей таблицы свойств.  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из значений перечисления, которое определяет внешний вид страницы свойств. Список возможных значений, см. в таблице перечисления в подразделе "Примечания" [CMFCPropertySheet::SetLook](#setlook).  
  
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
 Объект управления внутренней вкладки.  
  
### <a name="remarks"></a>Примечания  
 Страницы свойств можно задать, чтобы он отображался в различных стилей, например, элемент управления дерева список кнопки навигации или набор страниц с вкладками.  
  
 Перед вызовом этого метода необходимо вызвать [CMFCPropertySheet::SetLook](#setlook) метод, чтобы задать внешний вид элемента управления страниц свойств. Затем вызовите [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) метод для инициализации объекта внутренней вкладку элемента управления. Используйте этот метод для получения объекта управления вкладки и затем используйте этот объект для работы с вкладками в окне свойств.  
  
 Этот метод подтверждает в режиме отладки, если управления страниц свойств не настроена для отображения в формате Microsoft OneNote.  
  
##  <a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl  
 Инициализирует появление текущего элемента управления «Страница свойств».  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель окна элемента управления страниц свойств.  
  
### <a name="remarks"></a>Примечания  
 Управления страниц свойств могут использоваться в различных форм, таких как набор вкладок, дерево или список кнопок навигации. Используйте [CMFCPropertySheet::SetLook](#setlook) метод, чтобы задать внешний вид элемента управления страниц свойств.  
  
##  <a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage  
 Вызывается платформой при включении страницы свойств.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPage`  
 Указатель на объект страницы свойств, представляющий страницу свойство enabled.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод гарантирует, что свойство enabled страницы в области просмотра. Если стиль текущей страницы свойств содержит панель Microsoft Outlook, этот метод устанавливает соответствующую кнопку Outlook в установленном состоянии.  
  
##  <a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader  
 Вызывается платформой для рисования в заголовке страницы пользовательских свойств.  
  
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
 Ограничивающий прямоугольник, который определяет, где рисовать заголовок.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. При переопределении этого метода, вызвать [CMFCPropertySheet::EnablePageHeader](#enablepageheader) метод перед платформа вызывает этот метод.  
  
##  <a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage  
 Вызывается платформой для удаления страницы свойств из элемента управления «Дерево».  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPage`  
 Указатель на объект page свойство, представляющее страницу свойств для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
##  <a name="removecategory"></a>CMFCPropertySheet::RemoveCategory  
 Удаляет узел из элемента управления «Дерево».  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCategory`  
 Указатель на категории (узел) для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для удаления узла, который также называется категории, из дерева элемента управления. Используйте [CMFCPropertySheet::AddTreeCategory](#addtreecategory) метод для добавления узла в дерево.  
  
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
 Этот метод удаляет указанное свойство страницы и удаляет его соответствующее окно. На странице свойств объекта, `pPage` параметр указывает не уничтожается, пока не [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) закрытия окна.  
  
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
 Цвет прозрачное изображение. Части изображения, которые имеют этот цвет будет прозрачным. Значение по умолчанию — пурпурный цвет RGB(255,0,255).  
  
 [in] `hIcons`  
 Дескриптор существующего списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первом методе перегрузка синтаксис, `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если окно свойств в стиле Microsoft Outlook, платформа список кнопок навигации-элемент управления панели Outlook, в левой части страницы свойств. Используйте этот метод, чтобы задать список изображений для использования элементом управления панели Outlook.  
  
 Дополнительные сведения о методах, которые поддерживают этот метод в разделе [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) и [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Дополнительные сведения о задании свойств стиля в разделе [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="setlook"></a>CMFCPropertySheet::SetLook  
 Задает внешний вид таблицы свойств.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `look`  
 Одно из значений перечисления, которое определяет внешний вид страницы свойств. Стиль по умолчанию для свойств `CMFCPropertySheet::PropSheetLook_Tabs`. Дополнительные сведения см. в подразделе «Примечания».  
  
 [in] `nNavControlWidth`  
 Ширина элемента управления навигации, в пикселях. Значение по умолчанию — 100.  
  
### <a name="remarks"></a>Примечания  
 Чтобы отобразить окно свойств в стиль, используемый по умолчанию, этот метод перед созданием окна листа свойств.  
  
 В следующей таблице перечислены значений перечисления, которые могут быть указаны в `look` параметр.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(По умолчанию) Вкладка для каждой страницы свойств. Вкладки отображаются в верхней части страницы свойств и помещаются в стек, если имеется больше вкладок, чем может поместиться на одной строке.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Отображает список кнопок навигации в стиле Microsoft Outlook линейки с левой стороны страницы свойств. Каждая кнопка в списке соответствует страницы свойств. Платформа отображает стрелок прокрутки, если доступны дополнительные кнопки, чем может поместиться в видимой области списка.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|Отображает дерево в левой части страницы свойств. Страница свойств соответствует каждого родительского или дочернего узла дерева. Платформа отображает стрелками, если больше узлов, чем помещается в видимую область элемента управления дерева.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Отображает вкладки, в стиле Microsoft OneNote для каждой страницы свойств. Платформа framework содержит вкладки в верхней части страницы свойств и стрелок прокрутки, если имеются несколько вкладок, чем может поместиться в одну строку.|  
|`CMFCPropertySheet::PropSheetLook_List`|Отображает список с левой стороны страницы свойств. Каждый элемент списка соответствует страницы свойств. Платформа отображает стрелками, если существует несколько элементов списка, чем может поместиться в видимой области списка.|  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

