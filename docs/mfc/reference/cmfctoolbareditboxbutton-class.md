---
title: "Класс CMFCToolBarEditBoxButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton class
- SetACCData method
- OnCalculateSize method
- OnDraw method
- OnDrawOnCustomizeList method
- Serialize method
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
caps.latest.revision: 28
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
ms.openlocfilehash: 7f79c69c9f370f2d79752ed141affac3f97ce716
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbareditboxbutton-class"></a>Класс CMFCToolBarEditBoxButton
Кнопки панели инструментов, содержащий элемент управления редактированием ( [CEdit Class](../../mfc/reference/cedit-class.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Создает объект `CMFCToolBarEditBoxButton`.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Указывает, может ли пользователь растянуть кнопки во время настройки. (Переопределяет [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Копирует свойства кнопки панели инструментов, для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Создает новый элемент управления кнопки.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarEditBoxButton` объект в приложении, которое имеет идентификатор указанной команды.|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Получает текст элемента управления панели инструментов первого изменения с идентификатором указанную команду.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Получает идентификатор ресурса в контекстном меню, связанное с кнопкой.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Возвращает прямоугольник, ограничивающий части изменить поле «изменить».|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Возвращает указатель в поле редактирования, внедренный в кнопку.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Получает дескриптор окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Получает область клиентской области кнопки, которые должны быть перерисованы. (Переопределяет [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Определяет, отображается ли границы кнопки, когда пользователь нажимает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Определяет, имеют ли поле кнопки edit плоский стиль.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается инфраструктурой при добавлении кнопки **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается инфраструктурой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Вызывается инфраструктурой при нажатии кнопки мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Вызывается инфраструктурой при обработке родительского инструментов `WM_CTLCOLOR` сообщение. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Вызывается платформой для отображения кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Вызывается платформой для отображения кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается инфраструктурой при изменении глобальных шрифта. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Вызывается инфраструктурой при перемещении родительского инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Вызывается инфраструктурой при кнопка становится видимым или невидимым. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Вызывается инфраструктурой при инструментов родительской изменении ее размера или положения и это изменение приводит к изменить размер кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Вызывается средой во время обновления инструментов родительской его текст всплывающей подсказки. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Считывает этот объект из архива и записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Заполняет предоставленный `CAccessibilityData` объекта специальных возможностей данными из кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContents](#setcontents)|Задает текст в элементе управления кнопки.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Находит кнопке элемента управления правки, имеет идентификатор указанной команды, который задает текст в поле редактирования, кнопку.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Указывает идентификатор ресурса в контекстном меню, связанное с кнопкой.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Задает плоский внешний вид для кнопки изменения поля в приложении.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Указывает стиль кнопки. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Примечания  
 Чтобы добавить поле кнопку «Изменить» на панель инструментов, выполните следующие действия.  
  
 1. Зарезервируйте идентификатор фиктивный ресурс для кнопки в родительский ресурс панели инструментов.  
  
 2. Создать `CMFCToolBarEditBoxButton` объекта.  
  
 3. В обработчике сообщений, который обрабатывает `AFX_WM_RESETTOOLBAR` сообщений, заменить фиктивные кнопку новой кнопки поля со списком с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCToolBarEditBoxButton` класса. Примере показано, как указать, что пользователь можно растянуть кнопки во время настройки, отображалась границы кнопки, когда пользователь нажимает кнопку, задать текст в текстовом поле, указать плоский внешний вид для кнопки поле изменения в приложении и задать стиль элемента управления полем редактирования панели инструментов.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#40;](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>CMFCToolBarEditBoxButton::CanBeStretched  
 Указывает, может ли пользователь растянуть кнопки во время настройки.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не разрешается растянуть кнопки панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть во время настройки панели инструментов кнопку «Изменить поле».  
  
##  <a name="cmfctoolbareditboxbutton"></a>CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 Создает [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) объекта.  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Указывает идентификатор элемента управления.  
  
 [in] `iImage`  
 Задает отсчитываемый от нуля индекс значка панели инструментов. Изображение находится в [класса CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) объекта, [CMFCToolBar класс](../../mfc/reference/cmfctoolbar-class.md) поддерживает класс.  
  
 [in] `dwStyle`  
 Указывает стиль редактирования элемента управления.  
  
 [in] `iWidth`  
 Задает ширину в пикселях элемента управления поля ввода.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию задает стиль элемента управления редактирования следующие комбинации:  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 Ширина элемента управления по умолчанию — 150 пикселей.  
  
##  <a name="copyfrom"></a>CMFCToolBarEditBoxButton::CopyFrom  
 Копирует свойства кнопки панели инструментов, для текущей кнопки.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка «источник» для копирования.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для копирования другой кнопки панели инструментов эта кнопка панели инструментов. `src`должен быть типа `CMFCToolBarEditBoxButton`.  
  
##  <a name="createedit"></a>CMFCToolBarEditBoxButton::CreateEdit  
 Создает новый элемент управления кнопки.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pWndParent`  
 Указывает родительского окна элемента управления. Он не должен иметь значение NULL.  
  
 `[in] rect`  
 Задает размер и положение элемента управления поля ввода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный редактирования элемента управления; Это `NULL` при сбое создания элемента управления и вложения.  
  
### <a name="remarks"></a>Примечания  
 Создании `CMFCToolBarEditBoxButton`объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `CreateEdit,` которого управления редактированием Windows создает и присоединяет его к `CMFCToolBarEditBoxButton` объекта.  
  
##  <a name="getbycmd"></a>CMFCToolBarEditBoxButton::GetByCmd  
 Извлекает первый `CMFCToolBarEditBoxButton` объект в приложении, которое имеет идентификатор указанной команды.  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки для извлечения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый `CMFCToolBarEditBoxButton` объект в приложении, которое содержит заданный идентификатор команды, или `NULL` , если такой объект не существует.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служебной программы используется методы, такие как [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) и [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) задать или получить текст элемента управления панели инструментов первого изменения с идентификатором указанную команду.  
  
##  <a name="getcontentsall"></a>CMFCToolBarEditBoxButton::GetContentsAll  
 Получает текст элемента управления панели инструментов первого изменения с идентификатором указанную команду.  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки, из которого требуется извлечь содержимое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, который содержит текст элемента управления панели инструментов первого изменения с идентификатором указанную команду.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает пустую строку, если не `CMFCToolBarEditBoxButton` объекты имеют идентификатор указанной команды.  
  
##  <a name="getcontextmenuid"></a>CMFCToolBarEditBoxButton::GetContextMenuID  
 Получает идентификатор ресурса в контекстном меню, связанное с кнопкой.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса, связанный с кнопкой или 0, если кнопка имеет связанный контекстное меню не контекстного меню.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует идентификатор ресурса для создания в контекстном меню при щелчке на кнопке.  
  
##  <a name="geteditborder"></a>CMFCToolBarEditBoxButton::GetEditBorder  
 Возвращает прямоугольник, ограничивающий части изменить поле «изменить».  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectBorder`  
 Ссылку на `CRect` объект, получающий ограничивающего прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает прямоугольник, ограничивающий элемента управления в клиентских координатах. Он расширяет размер прямоугольника в каждом направлении на&1; пиксель.  
  
 [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) метод вызывает этот метод, когда он рисовал границу вокруг `CMFCToolBarEditBoxButton` объекта.  
  
##  <a name="geteditbox"></a>CMFCToolBarEditBoxButton::GetEditBox  
 Возвращает указатель на [CEdit Class](../../mfc/reference/cedit-class.md) управления, внедренный в кнопку.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CEdit Class](../../mfc/reference/cedit-class.md) элемент управления, содержащий кнопки. Это `NULL` Если `CEdit` еще не был создан элемент управления.  
  
### <a name="remarks"></a>Примечания  
 Можно создать `CEdit` управления путем вызова [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="gethwnd"></a>CMFCToolBarEditBoxButton::GetHwnd  
 Получает дескриптор окна, связанный с кнопкой панели инструментов.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна, связанный с кнопкой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метод возвращает дескриптор окна элемента управления редактирования части кнопки edit.  
  
##  <a name="getinvalidaterect"></a>CMFCToolBarEditBoxButton::GetInvalidateRect  
 Получает область клиентской области кнопки, которые должны быть перерисованы.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , определяющий область, должны быть перерисованы.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), включив в регионе области текста метки.  
  
##  <a name="havehotborder"></a>CMFCToolBarEditBoxButton::HaveHotBorder  
 Определяет, отображается ли границы кнопки, когда пользователь нажимает кнопку.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка отображается его границы, если установлен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), возвращая ненулевое значение, если элемент управления является видимым.  
  
##  <a name="isflatmode"></a>CMFCToolBarEditBoxButton::IsFlatMode  
 Определяет, имеют ли поле кнопки edit плоский стиль.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопки имеют плоский; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию кнопки изменения поля имеют плоский стиль. Используйте [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) метод, чтобы изменить плоский внешний вид для вашего приложения.  
  
##  <a name="notifycommand"></a>CMFCToolBarEditBoxButton::NotifyCommand  
 Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iNotifyCode`  
 Сообщение уведомления, связанный с командой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка обрабатывает `WM_COMMAND` сообщения, или `FALSE` для указания, что сообщения должны обрабатываться инструментов родительского.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда он собирается отправить [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение родительского окна.  
  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)), обрабатывая [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) уведомления. Для каждого поля ввода с тем же Идентификатором команды, что и данный объект он задает его текст метки текстовую метку для этого объекта.  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Вызывается инфраструктурой при добавлении кнопки **Настройка** диалоговое окно.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)), скопировав свойства из поля ввода в любой панели инструментов, который имеет тот же идентификатор команды, что и данный объект. Если элемент управления поле редактирования, имеет тот же идентификатор команды, что и данный объект имеет нет панели инструментов, этот метод не выполняет никаких действий.  
  
 Дополнительные сведения о **Настройка** диалоговом разделе [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Вызывается инфраструктурой при вставке кнопки в панели инструментов.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), повторно создав внутренний `CEdit` объекта.  
  
##  <a name="onclick"></a>CMFCToolBarEditBoxButton::OnClick  
 Вызывается инфраструктурой при нажатии кнопки мыши.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Не используется.  
  
 [in] `bDelay`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка обрабатывает сообщение щелкните; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)), возвращая ненулевое значение, если внутренний `CEdit` объект является видимым.  
  
##  <a name="onctlcolor"></a>CMFCToolBarEditBoxButton::OnCtlColor  
 Вызывается инфраструктурой при обработке родительского инструментов `WM_CTLCOLOR` сообщение.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, который отображает кнопки.  
  
 [in] `nCtlColor`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор кисти глобального окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)), задав цвета текста и фона контекста устройства, предоставленных глобального текста и цвета фона, соответственно.  
  
 Дополнительные сведения о глобальных параметров, доступных для вашего приложения, в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Вызывается инфраструктурой при изменении глобальных шрифта.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта элемента управления, глобальные шрифта.  
  
 Дополнительные сведения о глобальных параметров, доступных для вашего приложения, в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>CMFCToolBarEditBoxButton::OnMove  
 Вызывается инфраструктурой при перемещении родительского инструментов.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), обновив положение внутренний `CEdit` объекта  
  
##  <a name="onshow"></a>CMFCToolBarEditBoxButton::OnShow  
 Вызывается инфраструктурой при кнопка становится видимым или невидимым.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Указывает, видима ли кнопка. Если этот параметр равен `TRUE`, то кнопка отображается. В противном случае — кнопка не отображается.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), отображая кнопку, если `bShow` — `TRUE`. В противном случае этот метод скрывает кнопку.  
  
##  <a name="onsize"></a>CMFCToolBarEditBoxButton::OnSize  
 Вызывается инфраструктурой при инструментов родительской изменении ее размера или положения и это изменение приводит к изменить размер кнопки.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iSize`  
 Новая ширина кнопки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию, [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), обновив размер и положение внутреннего `CEdit` объекта.  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Вызывается средой во время обновления инструментов родительской его текст всплывающей подсказки.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Не используется.  
  
 [in] `iButtonIndex`  
 Не используется.  
  
 [in] `wndToolTip`  
 Элемент управления, отображающий текст всплывающей подсказки.  
  
 [выходной] `str`  
 Объект `CString` объект, который получает обновленный подсказку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод обновляет текст всплывающей подсказки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст подсказки, связанный с изменить части кнопки. Если внутренний `CEdit` объект `NULL` или дескриптор `CEdit` объекта не может определить существующему окну, этот метод не выполняет никаких действий и возвращает `FALSE`.  
  
##  <a name="setcontents"></a>CMFCToolBarEditBoxButton::SetContents  
 Задает текст в текстовом поле.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] sContents`  
 Определяет новый текст, чтобы задать.  
  
##  <a name="setcontentsall"></a>CMFCToolBarEditBoxButton::SetContentsAll  
 Находит [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) объекта, идентификатор указанной команды и задает указанный текст в его текстовое поле.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Указывает идентификатор элемента управления, для которого будет изменен текст команды.  
  
 [in] `strContents`  
 Определяет новый текст, чтобы задать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текст был задан; 0, если `CMFCToolBarEditBoxButton` элемента управления с заданным Идентификатором команды не существует.  
  
##  <a name="setcontextmenuid"></a>CMFCToolBarEditBoxButton::SetContextMenuID  
 Указывает идентификатор ресурса в контекстном меню, связанное с кнопкой.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор ресурса в контекстном меню.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует идентификатор ресурса для создания в контекстном меню при щелчке кнопки панели инструментов.  
  
##  <a name="setflatmode"></a>CMFCToolBarEditBoxButton::SetFlatMode  
 Задает плоский внешний вид для кнопки изменения поля в приложении.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFlat`  
 Плоский кнопок поля редактирования. Если этот параметр равен `TRUE`, включен плоский внешний вид; в противном случае отключается плоский внешний вид.  
  
### <a name="remarks"></a>Примечания  
 Плоский стиль по умолчанию для кнопки поле редактирования является `TRUE`. Используйте [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) метод для извлечения плоский внешний вид для вашего приложения.  
  
##  <a name="setstyle"></a>CMFCToolBarEditBoxButton::SetStyle  
 Задает стиль панели инструментов редактирования поля элемента управления.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nStyle`  
 Чтобы задать новый стиль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) для `nStyle` она также отключает текстовое поле, когда приложение находится в режиме Настройка и включает его, когда приложение не находится в режиме Настройка (см. [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) и [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). В разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md) список флагов допустимое значение стиля.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство: Добавление элементов управления в панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)




