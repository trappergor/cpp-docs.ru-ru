---
title: Класс CMFCToolBarEditBoxButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0bddd7274feb9ecde268a94d7e9a6e857c906650
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376822"
---
# <a name="cmfctoolbareditboxbutton-class"></a>Класс CMFCToolBarEditBoxButton
Кнопки панели инструментов, содержащий элемент управления редактированием ( [класс CEdit](../../mfc/reference/cedit-class.md)).  
  
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
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Создает новый элемент управления в кнопке.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarEditBoxButton` объекта в приложении, который имеет указанный идентификатор команды.|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Извлекает текст элемента управления панель инструментов первого изменения, имеющий указанный идентификатор команды.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Извлекает идентификатор ресурса, связанный с кнопкой контекстного меню.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Возвращает прямоугольник, ограничивающий части изменить поле «изменить».|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Возвращает указатель на поле редактирования, внедренных в кнопке.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Возвращает дескриптор окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Извлекает область клиентской области кнопки, которую требуется перерисовка. (Переопределяет [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Определяет, отображается ли границы кнопки, когда пользователь нажимает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Определяет, имеют ли кнопки, кнопки изменения плоский стиль.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщения. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Вызывается платформой, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Вызывается платформой при обработке родительского инструментов `WM_CTLCOLOR` сообщения. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Вызывается платформой для отрисовки кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Вызывается платформой для отрисовки кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается платформой при изменении глобальных шрифта. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Вызывается платформой при перемещении родительского инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Вызывается платформой при кнопка становится видимым или невидимым. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Вызывается платформой при инструментов родительского изменяет его размер или положение и это изменение приводит к изменить размер кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Вызывается платформой, когда родительский инструментов обновляет его текст всплывающей подсказки. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Заполняет предоставленный `CAccessibilityData` объект с данные специальных возможностей с помощью кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|Задает текст в элементе управления кнопки.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Находит кнопке правки элемента управления, который имеет указанный идентификатор команды и задает текст в поле редактирования, кнопка.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Указывает идентификатор ресурса, связанный с кнопкой контекстного меню.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Задает плоский внешний вид для кнопки, кнопки изменения в приложении.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Задает стиль кнопки. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Примечания  
 Чтобы добавить поле кнопку «Изменить» на панель инструментов, выполните следующие действия.  
  
 1. Зарезервировать идентификатора фиктивный ресурса для кнопки в родительский ресурс панели инструментов.  
  
 2. Создать `CMFCToolBarEditBoxButton` объекта.  
  
 3. В обработчике сообщений, который обрабатывает `AFX_WM_RESETTOOLBAR` сообщение, заменить фиктивный кнопку «Создать» поле со списком с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCToolBarEditBoxButton` класса. В примере показано, как указать, чтобы пользователь можно растянуть кнопки во время настройки, укажите, что границы кнопки отображается, когда пользователь нажимает кнопку, задавать текст в элементе текстового поля указать плоский внешний вид для кнопки, кнопки изменения в приложения Проверка подлинности и укажите стиль панели инструментов поле редактирования.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched  
 Указывает, может ли пользователь растянуть кнопки во время настройки.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа позволяет пользователю выполнить растяжение кнопки панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть кнопка изменения панели инструментов во время настройки.  
  
##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
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
 Задает отсчитываемый от нуля индекс изображение кнопки панели инструментов. Образ, находится в [класса CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) объекта, [CMFCToolBar класс](../../mfc/reference/cmfctoolbar-class.md) поддерживает класс.  
  
 [in] `dwStyle`  
 Указывает стиль редактирования элемента управления.  
  
 [in] `iWidth`  
 Задает ширину в пикселях элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию устанавливает следующие сочетания стиля элемента управления edit.  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 Ширина по умолчанию элемента управления — 150 пикселей.  
  
##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom  
 Копирует свойства другой кнопки панели инструментов в текущей кнопки.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка «источник» из которого выполняется копирование.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для копирования другую кнопку эта кнопка панели инструментов. `src` должен иметь тип `CMFCToolBarEditBoxButton`.  
  
##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit  
 Создает новый элемент управления в кнопке.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pWndParent`  
 Указывает родительского окна элемента управления. Оно не должно быть NULL.  
  
 `[in] rect`  
 Задает размер и положение элемента управления edit.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный редактирования элемента управления; Это `NULL` при сбое создания элемента управления и вложения.  
  
### <a name="remarks"></a>Примечания  
 Создании `CMFCToolBarEditBoxButton` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `CreateEdit`, который создает управления редактированием Windows и прикрепляет его к `CMFCToolBarEditBoxButton` объекта.  
  
##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd  
 Извлекает первый `CMFCToolBarEditBoxButton` объекта в приложении, который имеет указанный идентификатор команды.  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки для извлечения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый `CMFCToolBarEditBoxButton` объекта в приложении, который имеет указанный идентификатор команды, или `NULL` Если такой объект не существует.  
  
### <a name="remarks"></a>Примечания  
 Этот метод общей программы используется методами, такими как [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) и [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) задать или получить текст на первой панели инструментов поле редактирования элемент управления с указанным идентификатором команды.  
  
##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll  
 Извлекает текст элемента управления панель инструментов первого изменения, имеющий указанный идентификатор команды.  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки, из которого требуется извлечь содержимое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий текст элемента управления панель инструментов первого изменения, имеющий указанный идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает пустую строку, если нет `CMFCToolBarEditBoxButton` объекты имеют указанный идентификатор команды.  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID  
 Извлекает идентификатор ресурса, связанный с кнопкой контекстного меню.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса, связанный с кнопкой или 0, если кнопка имеет связанный контекстное меню не контекстного меню.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует идентификатор ресурса для создания в контекстном меню при щелчке на кнопке.  
  
##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder  
 Возвращает прямоугольник, ограничивающий части изменить поле «изменить».  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectBorder`  
 Ссылку на `CRect` объект, получающий ограничивающего прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает прямоугольник, ограничивающий элемента управления в клиентских координатах. Он расширяет размер прямоугольника в каждом направлении на один пиксель.  
  
 [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) метод вызывает этот метод при рисовании границ вокруг `CMFCToolBarEditBoxButton` объекта.  
  
##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox  
 Возвращает указатель на [класс CEdit](../../mfc/reference/cedit-class.md) управления, встроенные в кнопке.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [класс CEdit](../../mfc/reference/cedit-class.md) управления, который содержит кнопки. Это `NULL` Если `CEdit` управления еще не создан.  
  
### <a name="remarks"></a>Примечания  
 Вы создаете `CEdit` управления путем вызова [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd  
 Возвращает дескриптор окна, связанный с кнопкой панели инструментов.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна, связанный с кнопкой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метода, возвращая дескриптор окна элемента управления Правка части поле «изменить».  
  
##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect  
 Извлекает область клиентской области кнопки, которую требуется перерисовка.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , указывающий региона, в который требуется перерисовка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), путем включения в регионе области текста метки.  
  
##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder  
 Определяет, отображается ли границы кнопки, когда пользователь нажимает кнопку.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка отображается его границы, когда выбран; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), возвращая ненулевое значение, если элемент управления является видимым.  
  
##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode  
 Определяет, имеют ли кнопки, кнопки изменения плоский стиль.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопки имеют плоский; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию кнопки, кнопки изменения имеют плоский стиль. Используйте [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) метод, чтобы изменить плоский внешний вид для вашего приложения.  
  
##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand  
 Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщения.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iNotifyCode`  
 Сообщение уведомления, связанный с командой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если кнопки обрабатывает `WM_COMMAND` сообщения, или `FALSE` для указания, что сообщения должны обрабатываться родительским инструментов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при намерении отправки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение родительского окна.  
  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)), обрабатывая [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) уведомления. Для каждого поля ввода с тем же Идентификатором команды, что и данный объект он устанавливает его текстовая метка текстовую метку для этого объекта.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) путем копирования из поле ввода в любую панель инструментов, которая имеет тот же идентификатор команды, что и данный объект свойства. Если элемент управления поля редактирования, имеет тот же идентификатор команды, что и данный объект имеет без панелей инструментов, этот метод не выполняет никаких действий.  
  
 Дополнительные сведения о **Настройка** диалоговое окно, в разделе [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Вызывается платформой при вставке кнопки в панели инструментов.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), повторно создав внутренний `CEdit` объекта.  
  
##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick  
 Вызывается платформой, когда пользователь нажимает кнопку мыши.  
  
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
 Ненулевое значение, если кнопке обрабатывает сообщения нажмите кнопку. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)), возвращая ненулевое значение, если внутренний `CEdit` объект является видимым.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor  
 Вызывается платформой при обработке родительского инструментов `WM_CTLCOLOR` сообщения.  
  
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
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)), задав цветов текста и фона контекста устройства, предоставленный глобальный текста и цвета фона, соответственно.  
  
 Дополнительные сведения о глобальных параметрах, доступных для приложения см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Вызывается платформой при изменении глобальных шрифта.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта элемента управления, глобальные шрифта.  
  
 Дополнительные сведения о глобальных параметрах, доступных для приложения см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove  
 Вызывается платформой при перемещении родительского инструментов.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) путем обновления позиция внутренней `CEdit` объекта  
  
##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow  
 Вызывается платформой при кнопка становится видимым или невидимым.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Указывает, отображается ли кнопка. Если этот параметр равен `TRUE`, то кнопка отображается. В противном случае кнопка не отображается.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), отображая кнопки, если `bShow` — `TRUE`. В противном случае этот метод скрывает кнопку.  
  
##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize  
 Вызывается платформой при инструментов родительского изменяет его размер или положение и это изменение приводит к изменить размер кнопки.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iSize`  
 Новая ширина кнопки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию, [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), обновив размер и положение внутренней `CEdit` объекта.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Вызывается платформой, когда родительский инструментов обновляет его текст всплывающей подсказки.  
  
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
 Объект `CString` объект, получающий обновленный подсказка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод обновляет текст всплывающей подсказки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст подсказки, который связан с изменить часть кнопки. Если внутренний `CEdit` объект `NULL` или дескриптор `CEdit` объекта не может определить существующему окну, этот метод не выполняет никаких действий и возвращает `FALSE`.  
  
##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents  
 Задает текст в элементе текстового поля.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] sContents`  
 Указывает новый текст для задания.  
  
##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll  
 Находит [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) объект, который имеет указанный идентификатор команды и задает указанный текст в текстовом поле, его.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Указывает идентификатор элемента управления, для которого будет изменен текст команды.  
  
 [in] `strContents`  
 Указывает новый текст для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если был установлен текст; 0, если `CMFCToolBarEditBoxButton` элемент управления с заданным Идентификатором команды не существует.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID  
 Указывает идентификатор ресурса, связанный с кнопкой контекстного меню.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор ресурса в контекстном меню.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует идентификатор ресурса для создания в контекстном меню при щелчке правой кнопки панели инструментов.  
  
##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode  
 Задает плоский внешний вид для кнопки, кнопки изменения в приложении.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFlat`  
 Плоский стиль для кнопки, кнопки изменения. Если этот параметр равен `TRUE`, плоский внешний вид включен; в противном случае отключается плоский внешний вид.  
  
### <a name="remarks"></a>Примечания  
 Плоский стиль по умолчанию для кнопки, кнопки изменения — `TRUE`. Используйте [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) метод для извлечения плоский внешний вид для вашего приложения.  
  
##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle  
 Задает стиль панели инструментов редактирования поля элемента управления.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nStyle`  
 Чтобы задать новый стиль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод устанавливает [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) для `nStyle` она также отключает текстовое поле, когда приложение находится в режиме Настройка и включает его, когда приложение не находится в режиме Настройка (см. [CMFCToolBar: : SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) и [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). В разделе [стили элемента управления панель инструментов](../../mfc/reference/toolbar-control-styles.md) список флагов допустимое значение стиля.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)



