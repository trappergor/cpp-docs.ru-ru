---
title: Класс CMFCDropDownToolbarButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c65cf3070f199b013a0e85c1ae56764174fdc33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372538"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>Класс CMFCDropDownToolbarButton
Тип кнопки панели инструментов, который при нажатии ведет себя как обычная кнопка. Тем не менее, он открывает панель инструментов с раскрывающегося списка ( [CMFCDropDownToolBar класса](../../mfc/reference/cmfcdropdowntoolbar-class.md) Если пользователь нажимает и удерживает соответствующую кнопку на панели инструментов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Создает объект `CMFCDropDownToolbarButton`.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCDropDownToolbarButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Открывает панель инструментов с раскрывающегося списка.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Копирует текст с помощью кнопки панели инструментов в меню. (Переопределяет [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Извлекает панели инструментов раскрывающийся список, связанный с кнопкой.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Определяет, является ли открытый инструментов раскрывающегося списка.|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Определяет отображение кнопки с расширенной границей. (Переопределяет [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Вызывается платформой для обработки [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) сообщения. (Переопределяет `CMCToolBarButton::OnCancelMode`.)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Вызывается платформой, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Вызывается платформой, когда пользователь отпускает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Вызывается платформой при обработке родительского инструментов `WM_HELPHITTEST` сообщения. (Переопределяет [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Изменяет предоставленный меню, когда приложение отображает контекстное меню на панели инструментов родительской. (Переопределяет [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Вызывается платформой для отрисовки кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается платформой для отрисовки кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Задает команду по умолчанию, она используется, когда пользователь нажимает кнопку.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Указывает продолжительность времени, пользователь должен удерживайте кнопку мыши вниз до появления панели инструментов раскрывающегося списка.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCDropDownToolBarButton` отличается от обычного кнопки, у нее есть маленькую стрелку в правом нижнем углу кнопки. При выборе кнопки на панели инструментов раскрывающегося списка, платформа отображает ее значок на панели инструментов верхнего уровня (кнопка с маленькую стрелку в правом нижнем углу).  
  
 Сведения о реализации панели инструментов, раскрывающийся список см. в разделе [CMFCDropDownToolBar класса](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 `CMFCDropDownToolBarButton` Объекта могут быть экспортированы в [CMFCToolBarMenuButton класс](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта и отображаются в виде кнопки меню с помощью всплывающего меню.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom  
 Копирует свойства другой кнопки панели инструментов в текущей кнопки.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка «источник» из которого выполняется копирование.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для копирования другую кнопку эта кнопка панели инструментов. `src` должен иметь тип `CMFCDropDownToolbarButton`.  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
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
  
 Как правило, кнопки раскрывающегося списка используется текст из недавно использованных кнопки на панели инструментов, `pToolBar` указывает. Она использует текст, заданный параметром `lpszName` при кнопки преобразуется в кнопку меню или отображается в **команды** вкладке **Настройка** диалоговое окно. Дополнительные сведения о **Настройка** диалоговое окно, в разделе [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCDropDownToolbarButton` класса. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar  
 Открывает панель инструментов с раскрывающегося списка.  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Родительское окно фрейма раскрывающегося списка или `NULL` использовать родительское окно кнопки панели инструментов, раскрывающийся список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 [CMFCDropDownToolbarButton::OnClick](#onclick) метод вызывает этот метод, чтобы открыть раскрывающийся список инструментов, когда пользователь нажимает и удерживает соответствующую кнопку на панели инструментов.  
  
 Этот метод создает раскрывающийся список инструментов, используя [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) метод. Если закрепления панели инструментов родительского по вертикали, этот метод помещает раскрывающегося списка на панели инструментов либо в левой или правой части панели инструментов родительского, в зависимости от размера. В противном случае этот метод помещает инструментов раскрывающегося списка под родительским инструментов.  
  
 Этот метод завершается ошибкой, если `pWnd` — `NULL` и кнопки панели инструментов, раскрывающийся список не имеет родительского окна.  
  
##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton  
 Копирует текст с помощью кнопки панели инструментов в меню.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `menuButton`  
 Ссылка на целевой кнопкой меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает реализацию базового класса ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), а затем добавляет кнопку меню целевой всплывающего меню, которое содержит каждый элемент меню панели инструментов в этой кнопки. Этот метод не добавляет подменю всплывающего меню.  
  
 Этот метод завершается ошибкой, если панель инструментов родительского `m_pToolBar`, является `NULL` Возвращает реализацию базового класса или `FALSE`.  
  
##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar  
 Извлекает панели инструментов раскрывающийся список, связанный с кнопкой.  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Панель инструментов раскрывающийся список, связанный с кнопкой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `m_pToolBar` элемент данных.  
  
##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown  
 Определяет, является ли открытый инструментов раскрывающегося списка.  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если раскрывающийся список инструментов в данный момент открыт; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Платформа открывает панель инструментов раскрывающийся список с помощью [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Платформа закрывает раскрывающийся список инструментов, при нажатии кнопки мыши влево в неклиентской области инструментов, раскрывающийся список.  
  
##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize  
 Определяет отображение кнопки с расширенной границей.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопки панели инструментов могут отображаться с расширенной границей; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о расширенных границы, в разделе [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).  
  
##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay  
 Указывает продолжительность времени, пользователь должен удерживайте кнопку мыши вниз до появления панели инструментов раскрывающегося списка.  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Примечания  
 Задержка измеряется в миллисекундах. Значение по умолчанию — 500. Можно задать другой задержка, изменив значение этого элемента данных.  
  
##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize  
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
 Состояние закрепления панели инструментов родительского. Этот параметр является `TRUE` Если панель закреплена горизонтально или является перемещаемой или `FALSE` Если закрепления панели инструментов по вертикали.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `SIZE` структуру, содержащую размеры кнопки, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)), добавив Ширина стрелки раскрывающегося списка в горизонтальном направлении размер кнопки.  
  
##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd  
 Вызывается платформой при вставке кнопки в панели инструментов.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), сняв текстовая метка ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) и параметр [ CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) и [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) членов данных `FALSE`.  
  
##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick  
 Вызывается платформой, когда пользователь нажимает кнопку мыши.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Родительское окно кнопки панели инструментов.  
  
 [in] `bDelay`  
 `TRUE` Если сообщения должны обрабатываться с задержкой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопке обрабатывает сообщения нажмите кнопку. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), обновив состояние панели инструментов раскрывающегося списка.  
  
 Когда пользователь нажимает кнопку панели инструментов, этот метод создает таймер, который ожидает, длина времени, заданного параметром [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) член данных, а затем откроется в раскрывающемся списке панели инструментов с помощью [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Этот метод закрывает раскрывающегося списка на панели инструментов во второй раз, по нажатию кнопки панели инструментов.  
  
##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp  
 Вызывается платформой, когда пользователь отпускает кнопку мыши.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопке обрабатывает сообщения нажмите кнопку. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), обновив состояние панели инструментов раскрывающегося списка.  
  
 Этот метод останавливает таймер раскрывающимся списком, если он активен. Раскрывающийся список инструментов закрывается в том случае, если он открыт.  
  
 Дополнительные сведения о раскрывающимся списком и раскрывающимся списком таймера см. в разделе [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp  
 Вызывается платформой при обработке родительского инструментов `WM_HELPHITTEST` сообщения.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Родительское окно кнопки панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопке обрабатывает сообщение справки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) путем вызова [CMFCDropDownToolbarButton::OnClick](#onclick) метод с `bDelay` значение `FALSE` . Этот метод возвращает значение, которое возвращается [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
 Дополнительные сведения о `WM_HELPHITTEST message, see` [TN028: поддержка справки контекстно-зависимые](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu  
 Изменяет предоставленный меню, когда приложение отображает контекстное меню на панели инструментов родительской.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenu`  
 Меню для настройки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)), отключив следующие пункты меню:  
  
- **Изображение кнопки копирования**  
  
- **Внешний вид кнопки**  
  
- **Изображение**  
  
- **Text**  
  
- **Изображение и текст**  
  
 Переопределите этот метод для изменения в контекстном меню, платформа отображает в режим настройки.  
  
##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw  
 Вызывается платформой для отрисовки кнопки с помощью указанного стили и параметры.  
  
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
 Коллекция изображений панели инструментов, связанный с кнопкой.  
  
 [in] `bHorz`  
 Состояние закрепления панели инструментов родительского. Этот параметр является `TRUE` при кнопки закреплена горизонтально и `FALSE` когда кнопки подключено по вертикали.  
  
 [in] `bCustomizeMode`  
 Указывает, является ли панель инструментов в режим настройки. Этот параметр является `TRUE` Если панель инструментов находится в режим настройки и `FALSE` при панели инструментов не находится в режиме настройки.  
  
 [in] `bHighlight`  
 Указывает, выделяется ли кнопки. Этот параметр является `TRUE` при выделенной кнопки и `FALSE` при кнопки не выделяется.  
  
 [in] `bDrawBorder`  
 Указывает, следует ли отображать ее границы кнопки. Этот параметр является `TRUE` при кнопку отображать границу и `FALSE` при кнопки не должны отображать его границу.  
  
 [in] `bGrayDisabledButtons`  
 Указывает, следует ли затенять отключенных кнопок или использовать коллекции изображений отключено. Этот параметр является `TRUE` при отключенных кнопок должна быть затенена и `FALSE` при отключенном изображения коллекцию следует использовать этот метод.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для настройки панели инструментов кнопку рисования.  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 Вызывается платформой для отрисовки кнопки в **команды** области **Настройка** диалоговое окно.  
  
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
 Указывает, выбран ли кнопки. Если этот параметр равен `TRUE`, выборе этой кнопки. Если этот параметр равен `FALSE`, кнопка не выбрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина в пикселях кнопки в заданном контексте устройства.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается с помощью диалогового окна настройки ( **команды** вкладка) когда кнопки необходим для ее отображения в окне списка рисуемый владельцем.  
  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) изменением текста метки кнопки на имя кнопки (то есть значение `lpszName` параметр, который Вы передали конструктор).  
  
##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize  
 Считывает этот объект из архива или записывает его в архив.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
 `CArchive` Объект, из которого или сериализации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) путем сериализации идентификатор ресурса панели инструментов родительского. При загрузке архива ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) возвращает ненулевое значение), этот метод устанавливает `m_pToolBar` член данных на панели инструментов, которая содержит идентификатор сериализованного ресурса.  
  
##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand  
 Задает команду по умолчанию, она используется, когда пользователь нажимает кнопку.  
  
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
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)



