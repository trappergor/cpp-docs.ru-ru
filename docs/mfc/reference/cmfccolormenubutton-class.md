---
title: Класс CMFCColorMenuButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea9fddef1b032d1e17ea46229a992c23ca960822
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039028"
---
# <a name="cmfccolormenubutton-class"></a>Класс CMFCColorMenuButton
`CMFCColorMenuButton` Поддерживает класс команды меню или кнопки панели инструментов, которая запускает диалоговое окно выбора цвета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Создает объект `CMFCColorMenuButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отключает кнопка «automatic», расположенный выше обычного цветного кнопок. (Кнопка автоматического стандартной системы обозначается **автоматического**.)|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Включает отображение цветов системные цвета, конкретного документа.|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Включает и отключает «other» кнопки, расположенные ниже обычного цветного кнопок. (Кнопка «other» обозначается стандартной системы **Дополнительные цвета**.)|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Позволяет разделять выключить панель цвет.|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Получает текущий цвет автоматической.|  
|[CMFCColorMenuButton::GetColor](#getcolor)|Получает цвет текущей кнопки.|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Получает цвет, соответствующий указанному идентификатору команды.|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при изменении родительского окна.|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Откроется диалоговое окно выбора цвета.|  
|[CMFCColorMenuButton::SetColor](#setcolor)|Задает цвет текущий цвет кнопки.|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Задает цвет кнопки меню указанным цветом.|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Задает новое имя для указанного цвета.|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов, которые отображаются по `CMFCColorBar` объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Копирует другой кнопки панели инструментов в текущей кнопки.|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Создает диалоговое окно выбора цвета.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Указывает, поддерживаются ли пустое меню.|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|Вызывается платформой для отображения изображения на кнопке.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается платформой перед `CMFCColorMenuButton` объект отображается в списке диалогового окна настройки панели инструментов.|  
  
## <a name="remarks"></a>Примечания  
 Для замены исходного команды меню или панели инструментов кнопки с `CMFCColorMenuButton` объектов, создания `CMFCColorMenuButton` объект, задайте любом необходимые [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) стили, а затем вызовите `ReplaceButton` метод [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md) класса. Если настроить панель инструментов, вызовите [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) метод.  
  
 Диалоговое окно Выбор цветов создается во время обработки [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) обработчик событий. Обработчик событий уведомляет родительского фрейма с `WM_COMMAND` сообщения. `CMFCColorMenuButton` Объект отправляет идентификатор элемента управления, назначенный исходной команды меню или панели инструментов кнопки.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как создать и настроить цвет кнопки меню с помощью различных методов `CMFCColorMenuButton` класса. В примере `CPalette` объект сначала создается и затем используется для создания объекта `CMFCColorMenuButton` класса. `CMFCColorMenuButton` Объект затем настраивается, включив его автоматические и другие кнопки и установить ее цвет и число столбцов. Данный пример кода является частью [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolormenubutton.h  
  
##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton  
 Создает объект `CMFCColorMenuButton`.  
  
```  
CMFCColorMenuButton();

 
CMFCColorMenuButton(
    UINT uiCmdID,  
    LPCTSTR lpszText,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiCmdID*  
 Идентификатор команды кнопки.  
  
 [in] *lpszText*  
 Текст кнопки.  
  
 [in] *pPalette*  
 Указатель на кнопку цветовой палитры.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор является конструктором по умолчанию. Текущий цвет объекта и автоматической цветовой инициализируются в черный цвет (RGB (0, 0, 0)).  
  
 Второй конструктор инициализирует кнопку, чтобы цвет, соответствующий указанному идентификатору команды.  
  
##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom  
 Копирует один [CMFCToolBarMenuButton класса](../../mfc/reference/cmfctoolbarmenubutton-class.md)-производный объект в другой.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *src*  
 Кнопка источника для копирования.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы копировать объекты, которые являются производными от `CMFCColorMenuButton` объекта.  
  
##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu  
 Создает диалоговое окно выбора цвета.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект, представляющий диалоговое окно выбора цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда пользователь нажимает кнопку меню цвета.  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton  
 Включает и отключает кнопка «automatic», расположенный выше обычного цветного кнопок. (Кнопка автоматического стандартной системы обозначается **автоматического**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszLabel*  
 Задает текст кнопки, которое отображается, когда появится кнопка автоматического.  
  
 [in] *colorAutomatic*  
 Указывает новый автоматический цвет.  
  
 [in] *bEnable*  
 Указывает, является ли кнопка панели автоматический.  
  
### <a name="remarks"></a>Примечания  
 Использование автоматической кнопкой применяется текущий цвет по умолчанию.  
  
##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors  
 Включает отображение цветов системные цвета, конкретного документа.  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszLabel*  
 Задает текст кнопки.  
  
 [in] *bEnable*  
 `TRUE` для отображения цветов для конкретного документа или `FALSE` для отображения системных цветов.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для отображения текущих цветов документа или системные цвета палитры, при нажатии кнопки меню цвета.  
  
##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton  
 Включает и отключает «other» кнопки, расположенные ниже обычного цветного кнопок. (Кнопка «other» обозначается стандартной системы **Дополнительные цвета**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszLabel*  
 Задает текст кнопки.  
  
 [in] *bAltColorDlg*  
 Укажите `TRUE` для отображения `CMFCColorDialog` диалоговом или `FALSE` для отображения диалогового окна стандартный системный цвет.  
  
 [in] *bEnable*  
 Укажите `TRUE` для отображения кнопки «other»; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff  
 Позволяет разделять выключить панель цвет.  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiID*  
 Указывает идентификатор области перемещаемые.  
  
 [in] *nVertDockColumns*  
 Задает число столбцов в области по вертикали закрепленной цвет в перемещаемые состоянии.  
  
 [in] *nHorzDockRows*  
 Указывает количество строк для области по горизонтали закрепленной цвет в перемещаемые состоянии.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы включить функцию «перемещаемые» для панели «Цвет», возникающего при `CMFCColorMenuButton` нажатии кнопки.  
  
##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor  
 Получает текущий цвет автоматической.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение цвета, представляющий текущий автоматическое цвет.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения автоматической цветовой, который задается параметром [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).  
  
##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor  
 Получает цвет текущей кнопки.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID  
 Получает цвет, соответствующий указанному идентификатору команды.  
  
```  
static COLORREF GetColorByCmdID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiCmdID*  
 Идентификатор команды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, соответствующий указанному идентификатору команды.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, когда имеется несколько цвет кнопок в приложении. Когда пользователь нажимает кнопку цвета, кнопки отправляет его идентификатор команды сообщения WM_COMMAND родительским. `GetColorByCmdID` Метод использует идентификатор команды, чтобы получить соответствующий цвет.  
  
##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed  
 Указывает, поддерживаются ли пустое меню.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если разрешены пустое меню; в противном случае возвращается ноль.  
  
### <a name="remarks"></a>Примечания  
 Пустое меню поддерживаются по умолчанию. Переопределите этот метод, чтобы изменить это поведение в производном классе.  
  
##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd  
 Вызывается платформой при изменении родительского окна.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWndParent*  
 Указатель на новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw  
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
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rect*  
 Прямоугольник, ограничивающий область перерисовку.  
  
 [in] *pImages*  
 Указывает список изображений панели инструментов.  
  
 [in] *bHorz*  
 `TRUE` для указания, что панель инструментов находится в горизонтальной закрепленного состояния; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] *bCustomizeMode*  
 `TRUE` Чтобы указать, что приложение находится в режиме настройки. в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
 [in] *bHighlight*  
 `TRUE` Чтобы указать, что выделен кнопки; в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
 [in] *bDrawBorder*  
 `TRUE` Чтобы указать, отображается граница кнопки; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] *bGrayDisabledButtons*  
 `TRUE` Чтобы указать, отключенные кнопки отображены серым цветом (серым цветом) в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList  
 Вызывается платформой перед `CMFCColorMenuButton` объект отображается в списке диалогового окна настройки панели инструментов.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rect*  
 Прямоугольник, ограничивающий кнопки для отображения.  
  
 [in] *bSelected*  
 `TRUE` Указывает, что кнопка находится в выбранном состоянии; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина кнопки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при `CMFCColorMenuButton` объект отображается в поле со списком в процессе настройки панели инструментов.  
  
##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog  
 Откроется диалоговое окно выбора цвета.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *colorDefault*  
 Цвет по умолчанию, который выбран в диалоговом окне цветов.  
  
 [out] *colorRes*  
 Возвращает цвет, пользователем из диалогового окна цвет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь выбирает новый цвет; в противном случае возвращается ноль.  
  
### <a name="remarks"></a>Примечания  
 При нажатии кнопки, меню, вызовите этот метод, чтобы открыть диалоговое окно «цвет». Если возвращаемое значение имеет ненулевое значение, цвет, который пользователь выбирает сохраняется в *colorRes* параметра. Используйте [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) метод для переключения между окно стандартный цвет и [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно.  
  
##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor  
 Задает цвет текущий цвет кнопки.  
  
```  
virtual void SetColor(
    COLORREF clr,  
    BOOL bNotify=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *со средой clr*  
 Значение цвета RGB.  
  
 [in] *bNotify*  
 `TRUE` Чтобы применить *clr* цвет параметр, все связанные кнопку меню или кнопки панели инструментов; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для изменения цвета текущий цвет кнопки. Если *bNotify* параметр имеет ненулевое значение, цвет соответствующую кнопку на любой связанный всплывающего меню или панели инструментов изменить цвет, определенный по *clr* параметра.  
  
##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID  
 Задает цвет кнопки меню указанным цветом.  
  
```  
static void SetColorByCmdID(
    UINT uiCmdID,  
    COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiCmdID*  
 Идентификатор ресурса, цвет кнопки меню.  
  
 [in] *цвет*  
 Значение цвета RGB.  
  
##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName  
 Задает новое имя для указанного цвета.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *цвет*  
 RGB-значение цвета, имя которого изменяется.  
  
 [in] *strName*  
 Новое имя цвета.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber  
 Задает число столбцов для отображения в элементе управления выбора цвета ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта).  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nColumns*  
 Число столбцов для отображения.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)
