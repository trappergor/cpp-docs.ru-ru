---
title: "Класс CMFCDropDownToolbarButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolbarButton class
- OnCancelMode method
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 24398ddb605489bf9677bd493a1bc1f490d583b9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdowntoolbarbutton-class"></a>Класс CMFCDropDownToolbarButton
Тип кнопки панели инструментов, который при нажатии ведет себя как обычная кнопка. Тем не менее, он открывает раскрывающемся списке панели инструментов ( [CMFCDropDownToolBar класса](../../mfc/reference/cmfcdropdowntoolbar-class.md) Если пользователь нажимает и удерживает нажатую кнопку панели инструментов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Создает объект `CMFCDropDownToolbarButton`.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Копирует свойства кнопки панели инструментов, для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCDropDownToolbarButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Открытие раскрывающегося списка на панели инструментов.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Копирует текст из кнопки панели инструментов меню. (Переопределяет [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Извлекает панели инструментов раскрывающийся список, связанный с кнопкой.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Определяет, является ли панель инструментов в раскрывающемся списке открытые в настоящий момент.|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Определяет отображение кнопки с расширенной рамкой. (Переопределяет [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Вызывается платформой для обработки [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) сообщений. (Переопределяет `CMCToolBarButton::OnCancelMode`.)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается инфраструктурой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Вызывается инфраструктурой при нажатии кнопки мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Вызывается платформой, когда пользователь отпускает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Вызывается инфраструктурой при обработке родительского инструментов `WM_HELPHITTEST` сообщение. (Переопределяет [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Изменяет предоставленный меню, когда приложение отображает контекстное меню на панели инструментов родительской. (Переопределяет [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Вызывается платформой для отображения кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается платформой для отображения кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Считывает этот объект из архива и записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Задает команды по умолчанию, она используется, когда пользователь нажимает кнопку.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Задает интервал времени, пользователь должен нажатой кнопку мыши до появления панели инструментов в раскрывающемся списке.|  
  
## <a name="remarks"></a>Примечания  
 A `CMFCDropDownToolBarButton` отличается от обычной кнопки тем, что маленькая стрелка в правом нижнем углу кнопку. После пользователь выбирает кнопку на панели инструментов в раскрывающемся списке, платформа отображает его значок на панели инструментов верхнего уровня (кнопка с маленькая стрелка в правом нижнем углу).  
  
 Сведения о способах реализации панели инструментов, раскрывающийся список в разделе [CMFCDropDownToolBar класса](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 `CMFCDropDownToolBarButton` Объекта могут быть экспортированы в [CMFCToolBarMenuButton класс](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта и отображаются в виде кнопки меню с помощью всплывающего меню.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>CMFCDropDownToolbarButton::CopyFrom  
 Копирует свойства кнопки панели инструментов, для текущей кнопки.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка «источник» для копирования.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для копирования другой кнопки панели инструментов эта кнопка панели инструментов. `src`должен быть типа `CMFCDropDownToolbarButton`.  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 Создает объект `CMFCDropDownToolbarButton`.  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 По умолчанию текст кнопки.  
  
 [in] `pToolBar`  
 Указатель на `CMFCDropDownToolBar` объект, который отображается, когда пользователь нажимает кнопку.  
  
### <a name="remarks"></a>Примечания  
 Вторая перегрузка конструктора копирует разворачивающуюся кнопку первую кнопку на панели инструментов, `pToolBar` указывает.  
  
 Как правило, кнопки панели инструментов в раскрывающемся списке использует текст из недавно использованных кнопки на панели инструментов, `pToolBar` указывает. Он использует текст, заданный параметром `lpszName` при кнопки преобразуется в меню кнопки или отображается в **команды** вкладке **Настройка** диалоговое окно. Дополнительные сведения о **Настройка** диалоговом разделе [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCDropDownToolbarButton` класса. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#31;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::DropDownToolbar  
 Открытие раскрывающегося списка на панели инструментов.  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Родительское окно фрейма раскрывающегося списка или `NULL` использовать родительское окно кнопки панели инструментов в раскрывающемся списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 [CMFCDropDownToolbarButton::OnClick](#onclick) метод вызывает этот метод, чтобы открыть панель инструментов раскрывающегося списка, когда пользователь нажимает и удерживает нажатую кнопку панели инструментов.  
  
 Этот метод создает раскрывающийся список инструментов с помощью [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) метод. Если родительский инструментов закреплена вертикально, этот метод помещает раскрывающегося списка на панели инструментов либо в левой или правой части панели инструментов родительской, в зависимости от размера. В противном случае этот метод помещает инструментов раскрывающегося списка под родительским инструментов.  
  
 Этот метод не выполняется, если `pWnd` — `NULL` и кнопки панели инструментов в раскрывающемся списке не имеет родительского окна.  
  
##  <a name="exporttomenubutton"></a>CMFCDropDownToolbarButton::ExportToMenuButton  
 Копирует текст из кнопки панели инструментов меню.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `menuButton`  
 Ссылка на кнопке меню целевой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает реализацию базового класса ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), а затем добавляется к кнопке меню целевой всплывающего меню, которое содержит каждый элемент меню инструментов на этой кнопке. Этот метод не добавляет подменю всплывающего меню.  
  
 Этот метод не выполняется, если панель инструментов родительского `m_pToolBar`, является `NULL` или возвращает реализацию базового класса `FALSE`.  
  
##  <a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton::GetDropDownToolBar  
 Извлекает панели инструментов раскрывающийся список, связанный с кнопкой.  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Панель инструментов раскрывающийся список, связанный с кнопкой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `m_pToolBar` элемент данных.  
  
##  <a name="isdropdown"></a>CMFCDropDownToolbarButton::IsDropDown  
 Определяет, является ли панель инструментов в раскрывающемся списке открытые в настоящий момент.  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если раскрывающийся список инструментов в данный момент открыт; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Платформа открывает раскрывающемся списке панели инструментов с помощью [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Платформа закрывает инструментов раскрывающегося списка при нажатии кнопки мыши влево в неклиентской области в раскрывающемся списке панели инструментов.  
  
##  <a name="isextrasize"></a>CMFCDropDownToolbarButton::IsExtraSize  
 Определяет отображение кнопки с расширенной рамкой.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопки панели инструментов могут отображаться с расширенной рамкой; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о расширенных границы, в разделе [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).  
  
##  <a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton::m_uiShowBarDelay  
 Задает интервал времени, пользователь должен нажатой кнопку мыши до появления панели инструментов в раскрывающемся списке.  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Примечания  
 Задержка измеряется в миллисекундах. Значение по умолчанию — 500. Можно задать другой задержки, изменив значение этого элемента общих данных.  
  
##  <a name="oncalculatesize"></a>CMFCDropDownToolbarButton::OnCalculateSize  
 Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, который отображает кнопки.  
  
 [in] `sizeDefault`  
 По умолчанию размер кнопки.  
  
 [in] `bHorz`  
 Состояние закрепления панели инструментов родительской. Этот параметр является `TRUE` Если панель закреплена горизонтально или является перемещаемой или `FALSE` Если вертикально закрепленной панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `SIZE` структуру, содержащую размеры кнопки, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)), добавив Ширина стрелки раскрывающегося списка горизонтальный размер размер кнопки.  
  
##  <a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton::OnChangeParentWnd  
 Вызывается инфраструктурой при вставке кнопки в панели инструментов.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), сняв текстовую метку ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) и параметр [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) и [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) данные-члены `FALSE`.  
  
##  <a name="onclick"></a>CMFCDropDownToolbarButton::OnClick  
 Вызывается инфраструктурой при нажатии кнопки мыши.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Родительское окно кнопки панели инструментов.  
  
 [in] `bDelay`  
 `TRUE`Если сообщения должны обрабатываться с задержкой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка обрабатывает сообщение щелкните; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), обновив состояние панели инструментов в раскрывающемся списке.  
  
 Когда пользователь щелкает кнопку панели инструментов, этот метод создает таймер, который ожидает в течение указанного времени, заданные [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) данные-член, а затем открывает раскрывающемся списке панели инструментов с помощью [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Этот метод закрывает во второй раз при нажатии пользователем кнопки панели инструментов панели инструментов в раскрывающемся списке.  
  
##  <a name="onclickup"></a>CMFCDropDownToolbarButton::OnClickUp  
 Вызывается платформой, когда пользователь отпускает кнопку мыши.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка обрабатывает сообщение щелкните; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), обновив состояние панели инструментов в раскрывающемся списке.  
  
 Этот метод останавливает таймер раскрывающимся списком, если он активен. Раскрывающийся список инструментов закрывается в том случае, если она открыта.  
  
 Дополнительные сведения о раскрывающимся списком и раскрывающимся списком таймера в разделе [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
##  <a name="oncontexthelp"></a>CMFCDropDownToolbarButton::OnContextHelp  
 Вызывается инфраструктурой при обработке родительского инструментов `WM_HELPHITTEST` сообщение.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Родительское окно кнопки панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка обрабатывает сообщение справки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) путем вызова [CMFCDropDownToolbarButton::OnClick](#onclick) метод `bDelay` значение `FALSE`. Этот метод возвращает значение, которое возвращается [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
 Дополнительные сведения о `WM_HELPHITTEST message, see` [TN028: поддержка справки контекстно-зависимые](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="oncustomizemenu"></a>CMFCDropDownToolbarButton::OnCustomizeMenu  
 Изменяет предоставленный меню, когда приложение отображает контекстное меню на панели инструментов родительской.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenu`  
 Для настройки меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)), отключив следующие пункты меню:  
  
- **Изображение кнопки копирования**  
  
- **Внешний вид кнопки**  
  
- **Изображение**  
  
- **Текст**  
  
- **Изображение и текст**  
  
 Переопределите этот метод для изменения контекстное меню, которое отображает платформа в режим настройки.  
  
##  <a name="ondraw"></a>CMFCDropDownToolbarButton::OnDraw  
 Вызывается платформой для отображения кнопки с помощью указанного стили и параметры.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, который отображает кнопки.  
  
 [in] `rect`  
 Ограничивающий прямоугольник кнопки.  
  
 [in] `pImages`  
 Коллекция изображений на панели инструментов, связанный с кнопкой.  
  
 [in] `bHorz`  
 Состояние закрепления панели инструментов родительской. Этот параметр является `TRUE` при кнопки закреплена горизонтально и `FALSE` при прикреплении кнопки по вертикали.  
  
 [in] `bCustomizeMode`  
 Указывает, является ли режим настройки панели инструментов. Этот параметр является `TRUE` Если панель инструментов находится в режиме настройки и `FALSE` Если панели инструментов не находится в режиме настройки.  
  
 [in] `bHighlight`  
 Указывает, выделяется ли кнопки. Этот параметр является `TRUE` когда выделена кнопка и `FALSE` при кнопки не выделяется.  
  
 [in] `bDrawBorder`  
 Указывает, следует ли отображать его границы кнопки. Этот параметр является `TRUE` при кнопки следует отображать границу и `FALSE` при кнопки не должна отображаться граница.  
  
 [in] `bGrayDisabledButtons`  
 Указывает, следует ли затенять отключенных кнопок или использование коллекции изображений отключено. Этот параметр является `TRUE` при отключенных кнопок должна быть затенена и `FALSE` при отключенном изображения коллекцию следует использовать этот метод.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для настройки панели инструментов кнопку рисования.  
  
##  <a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 Вызывается платформой для отображения кнопки в **команды** области **Настройка** диалоговое окно.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, который отображает кнопки.  
  
 [in] `rect`  
 Ограничивающий прямоугольник кнопки.  
  
 [in] `bSelected`  
 Указывает, выбран ли кнопки. Если этот параметр равен `TRUE`, выбранной кнопки. Если этот параметр равен `FALSE`, кнопка не выбрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях, кнопки в заданном контексте устройства.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается диалоговое окно настройки ( **команды** вкладка) когда кнопки, необходимые для ее отображения в списке рисование владельцем.  
  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)), изменив текст метки кнопки на имя кнопки (то есть значение `lpszName` параметр, передаваемый конструктору).  
  
##  <a name="serialize"></a>CMFCDropDownToolbarButton::Serialize  
 Считывает этот объект из архива и записывает его в архив.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
 `CArchive` Объект, из которого или сериализации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)), сериализация идентификатор ресурса панели инструментов родительской. После загрузки архива ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) возвращает ненулевое значение), этот метод задает `m_pToolBar` член данных на панель инструментов, содержащий сериализованный ресурса.  
  
##  <a name="setdefaultcommand"></a>CMFCDropDownToolbarButton::SetDefaultCommand  
 Задает команды по умолчанию, она используется, когда пользователь нажимает кнопку.  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для указания команды по умолчанию, которую платформа выполняет, когда пользователь нажимает кнопку. Элемент с Идентификатором команды, заданные `uiCmd` должен быть расположен на панели инструментов родительской раскрывающегося списка.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [Пошаговое руководство: Добавление элементов управления в панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)




