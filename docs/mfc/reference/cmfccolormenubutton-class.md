---
title: "Класс CMFCColorMenuButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorMenuButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorMenuButton class
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
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
ms.openlocfilehash: a9b1e7a3dbfe4d98b3d51850723eb22ec1f9da06
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolormenubutton-class"></a>Класс CMFCColorMenuButton
`CMFCColorMenuButton` Поддерживает класс команды меню или кнопки панели инструментов, запускающие диалоговое окно выбора цвета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Создает объект `CMFCColorMenuButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отключает кнопка «автоматический», расположенный выше регулярного цветные кнопки. (Кнопка автоматического стандартной системе обозначается **автоматическое**.)|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Позволяет отображать цветов конкретного документа вместо системных цветов.|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Включает и отключает «other» кнопки, расположенные ниже регулярных цветные кнопки. (Кнопка «other» обозначается стандартной системы **Дополнительные цвета... **.)|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Дает возможность отрыв области цвета.|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Получает текущий автоматическое цвет.|  
|[CMFCColorMenuButton::GetColor](#getcolor)|Получает цвет текущей кнопки.|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Получает цвет, соответствующий указанному идентификатору команды.|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается инфраструктурой при изменении родительского окна.|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Откроется диалоговое окно выбора цвета.|  
|[CMFCColorMenuButton::SetColor](#setcolor)|Задает цвет текущего цвета кнопки.|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Задает цвет кнопки меню указанный цвет.|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Задает новое имя для указанного цвета.|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов, которые отображаются по `CMFCColorBar` объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Копирует другой кнопки панели инструментов в текущей кнопки.|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Создает диалоговое окно выбора цвета.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Указывает, поддерживаются ли пустое меню.|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|Вызывается платформой для отображения изображения на кнопке.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается средой перед `CMFCColorMenuButton` объект отображается в списке диалогового окна настройки панели инструментов.|  
  
## <a name="remarks"></a>Примечания  
 Для замены исходного меню команды или кнопки панели инструментов с `CMFCColorMenuButton` объекта, создайте `CMFCColorMenuButton` объекта, задайте все необходимые [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) стили, а затем вызвать `ReplaceButton` метод [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md) класса. Если настроить панель инструментов, вызвать [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) метод.  
  
 Диалоговое окно выбора цвета создается во время обработки [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) обработчик событий. Обработчик событий уведомляет родительского фрейма с `WM_COMMAND` сообщение. `CMFCColorMenuButton` Объект отправляет идентификатор элемента управления, присвоенный исходное меню команды или кнопки панели инструментов.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание и настройка кнопка меню цвета с помощью различных методов в `CMFCColorMenuButton` класса. В примере `CPalette` сначала создается объект, а затем используется для создания объекта `CMFCColorMenuButton` класса. `CMFCColorMenuButton` Объект затем настраивается, обеспечивая его автоматическое и другие кнопки и задав ее цвет и число столбцов. Данный пример кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#5;](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad №&6;](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolormenubutton.h  
  
##  <a name="a-namecmfccolormenubuttona--cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a>CMFCColorMenuButton::CMFCColorMenuButton  
 Создает объект `CMFCColorMenuButton`.  
  
```  
CMFCColorMenuButton();

 
CMFCColorMenuButton(
    UINT uiCmdID,  
    LPCTSTR lpszText,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды кнопки.  
  
 [in] `lpszText`  
 Текст кнопки.  
  
 [in] `pPalette`  
 Указатель на кнопку цвет палитры.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор-это конструктор по умолчанию. Текущий цвет объекта, а автоматическое инициализируются в черный цвет (RGB (0, 0, 0)).  
  
 Второй конструктор инициализирует кнопки цвет, соответствующий указанному идентификатору команды.  
  
##  <a name="a-namecopyfroma--cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFCColorMenuButton::CopyFrom  
 Копирует один [CMFCToolBarMenuButton класса](../../mfc/reference/cmfctoolbarmenubutton-class.md)-производный объект в другой.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Кнопка источник для копирования.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы копировать объекты, которые являются производными от `CMFCColorMenuButton` объекта.  
  
##  <a name="a-namecreatepopupmenua--cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFCColorMenuButton::CreatePopupMenu  
 Создает диалоговое окно выбора цвета.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект, представляющий диалоговое окно выбора цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при нажатии кнопка меню цвета.  
  
##  <a name="a-nameenableautomaticbuttona--cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorMenuButton::EnableAutomaticButton  
 Включает и отключает кнопка «автоматический», расположенный выше регулярного цветные кнопки. (Кнопка автоматического стандартной системе обозначается **автоматическое**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Задает текст кнопки, отображаемый, когда кнопка автоматического.  
  
 [in] `colorAutomatic`  
 Указывает новый автоматическое цвет.  
  
 [in] `bEnable`  
 Указывает, является ли кнопка панели автоматический.  
  
### <a name="remarks"></a>Примечания  
 Кнопка автоматического применяется текущий цвет по умолчанию.  
  
##  <a name="a-nameenabledocumentcolorsa--cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a>CMFCColorMenuButton::EnableDocumentColors  
 Позволяет отображать цветов конкретного документа вместо системных цветов.  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Задает текст кнопки.  
  
 [in] `bEnable`  
 `TRUE`для отображения конкретного документа цветов или `FALSE` для отображения системных цветов.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для отображения цвета текущего документа или системные цвета палитры, когда пользователь нажимает кнопку меню цвета.  
  
##  <a name="a-nameenableotherbuttona--cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorMenuButton::EnableOtherButton  
 Включает и отключает «other» кнопки, расположенные ниже регулярных цветные кнопки. (Кнопка «other» обозначается стандартной системы **Дополнительные цвета... **.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Задает текст кнопки.  
  
 [in] `bAltColorDlg`  
 Укажите `TRUE` для отображения `CMFCColorDialog` диалоговом или `FALSE` для отображения диалогового окна стандартный системный цвет.  
  
 [in] `bEnable`  
 Укажите `TRUE` для отображения кнопки «other»; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenabletearoffa--cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a>CMFCColorMenuButton::EnableTearOff  
 Дает возможность отрыв области цвета.  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Указывает идентификатор области перемещаемые.  
  
 [in] `nVertDockColumns`  
 Указывает количество столбцов в области по вертикали закрепленной цвет в перемещаемые состоянии.  
  
 [in] `nHorzDockRows`  
 Указывает количество строк для области по горизонтали закрепленной цвет в перемещаемые состоянии.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для включения функции «перемещаемое» области цвета, возникающего при `CMFCColorMenuButton` нажатии кнопки.  
  
##  <a name="a-namegetautomaticcolora--cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCColorMenuButton::GetAutomaticColor  
 Получает текущий автоматическое цвет.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение цвета, представляющий текущий автоматическое цвет.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения автоматическое цвет, заданный свойством [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).  
  
##  <a name="a-namegetcolora--cmfccolormenubuttongetcolor"></a><a name="getcolor"></a>CMFCColorMenuButton::GetColor  
 Получает цвет текущей кнопки.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcolorbycmdida--cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a>CMFCColorMenuButton::GetColorByCmdID  
 Получает цвет, соответствующий указанному идентификатору команды.  
  
```  
static COLORREF GetColorByCmdID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, который соответствует указанному идентификатору команды.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод при наличии нескольких цветные кнопки в приложении. Когда пользователь нажимает кнопку цвета, кнопки отправляет его идентификатор команды в `WM_COMMAND` сообщения с родительским. `GetColorByCmdID` Метод использует идентификатор команды, чтобы получить соответствующий цвет.  
  
##  <a name="a-nameisemptymenualloweda--cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFCColorMenuButton::IsEmptyMenuAllowed  
 Указывает, поддерживаются ли пустое меню.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если разрешены пустое меню; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию поддерживаются пустое меню. Переопределите этот метод, чтобы изменить это поведение, в производном классе.  
  
##  <a name="a-nameonchangeparentwnda--cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCColorMenuButton::OnChangeParentWnd  
 Вызывается инфраструктурой при изменении родительского окна.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawa--cmfccolormenubuttonondraw"></a><a name="ondraw"></a>CMFCColorMenuButton::OnDraw  
 Вызывается платформой для отображения изображения на кнопке.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, ограничивающий область перерисовку.  
  
 [in] `pImages`  
 Указывает список изображений панели инструментов.  
  
 [in] `bHorz`  
 `TRUE`Чтобы указать, что в горизонтальной панели инструментов закреплены состояния; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] `bCustomizeMode`  
 `TRUE`Чтобы указать, что приложение находится в режиме настройки. в противном случае — `FALSE`. Значение по умолчанию — `FALSE`.  
  
 [in] `bHighlight`  
 `TRUE`Чтобы указать, что кнопка выделена; в противном случае — `FALSE`. Значение по умолчанию — `FALSE`.  
  
 [in] `bDrawBorder`  
 `TRUE`Чтобы указать, что граница кнопки отображается; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`Указание того, что отключена, кнопки отображены серым цветом (как недоступные) в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawoncustomizelista--cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCColorMenuButton::OnDrawOnCustomizeList  
 Вызывается средой перед `CMFCColorMenuButton` объект отображается в списке диалогового окна настройки панели инструментов.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, ограничивающий кнопки для отображения.  
  
 [in] `bSelected`  
 `TRUE`Указывает, что кнопка находится в выбранном состоянии; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина кнопки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при `CMFCColorMenuButton` объект отображается в поле со списком в процессе настройки панели инструментов.  
  
##  <a name="a-nameopencolordialoga--cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a>CMFCColorMenuButton::OpenColorDialog  
 Откроется диалоговое окно выбора цвета.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colorDefault`  
 Цвет по умолчанию, который выбран в диалоговом окне цветов.  
  
 [выходной] `colorRes`  
 Возвращает цвет, выбранный пользователем в диалоговом окне цвет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь выбирает новый цвет. в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 При нажатии кнопки меню вызовите этот метод, чтобы открыть диалоговое окно. Если возвращаемое значение отлично от нуля, цвет, который пользователь выбирает хранится в `colorRes` параметр. Используйте [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) метод для переключения между окно стандартный цвет и [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно.  
  
##  <a name="a-namesetcolora--cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a>CMFCColorMenuButton::SetColor  
 Задает цвет текущего цвета кнопки.  
  
```  
virtual void SetColor(
    COLORREF clr,  
    BOOL bNotify=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clr`  
 Значение цвета RGB.  
  
 [in] `bNotify`  
 `TRUE`Чтобы применить `clr` параметр цвет любой связанный кнопку меню или кнопки панели инструментов; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для изменения цвета кнопки текущего цвета. Если `bNotify` параметр имеет ненулевое значение, цвет соответствующую кнопку на любой связанный всплывающее меню или панель инструментов меняется на цвет, определенный параметром `clr` параметр.  
  
##  <a name="a-namesetcolorbycmdida--cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a>CMFCColorMenuButton::SetColorByCmdID  
 Задает цвет кнопки меню указанный цвет.  
  
```  
static void SetColorByCmdID(
    UINT uiCmdID,  
    COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор ресурса кнопка меню цвета.  
  
 [in] `color`  
 Значение цвета RGB.  
  
##  <a name="a-namesetcolornamea--cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a>CMFCColorMenuButton::SetColorName  
 Задает новое имя для указанного цвета.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 RGB-значение цвета, имя которого изменяется.  
  
 [in] `strName`  
 Новое имя цвета.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetcolumnsnumbera--cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCColorMenuButton::SetColumnsNumber  
 Задает количество столбцов для отображения в элементе управления выбора цвета ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта).  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nColumns`  
 Число столбцов для отображения.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)

