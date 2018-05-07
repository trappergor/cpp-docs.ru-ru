---
title: Класс CMFCColorButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cea6fc2a543a528a0838479b2c47bea99f21cf96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccolorbutton-class"></a>Класс CMFCColorButton
`CMFCColorButton` И [CMFCColorBar класса](../../mfc/reference/cmfccolorbar-class.md) классы используются совместно для реализации управление палитрой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Создает новое `CMFCColorButton` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отключает кнопка «automatic», расположенный выше обычного цветного кнопок. (Кнопка автоматического стандартной системы обозначается **автоматического**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Включает и отключает «other» кнопки, расположенные ниже обычного цветного кнопок. (Кнопка «other» обозначается стандартной системы **Дополнительные цвета**.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Получает текущий цвет автоматической.|  
|[CMFCColorButton::GetColor](#getcolor)|Получает цвет кнопки.|  
|[CMFCColorButton::SetColor](#setcolor)|Задает цвет кнопки.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Задает имя цвета.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов в диалоговом окне выбора цвета.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Задает список цветов относящиеся к документам, которые отображаются в диалоговом окне выбора цвета.|  
|[CMFCColorButton::SetPalette](#setpalette)|Палитра цветов стандартные.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Изменение размера кнопки в зависимости от его размера текста и изображений.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Указывает, отображается ли кнопка текущего цвета в визуальном стиле Windows XP.|  
|[CMFCColorButton::OnDraw](#ondraw)|Вызывается платформой для отображения изображения кнопки.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Вызывается платформой для отображения границы кнопки.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается платформой для отображения прямоугольник фокуса, когда кнопка имеет фокус.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Вызывается платформой при отобразится диалоговое окно Выбор цветов.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Инициализирует `m_pPalette` защищенные данные-члены указанного палитры или палитры системы по умолчанию.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Вызывается платформой, когда пользователь выбирает цвет из палитры диалогового окна выбора цвета.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|`m_bAltColorDlg`|Значение типа Boolean. Если `TRUE`, платформа отображает [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалогового окна "цвета", когда *других* кнопки, или если `FALSE`, диалоговое окно Цвет системы. Значение по умолчанию — `TRUE`. Дополнительные сведения см. в разделе [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Значение типа Boolean. Если `TRUE`, платформа с фокусом, в меню Цвет при отображении меню или `FALSE`, не изменяет фокус. Значение по умолчанию — `TRUE`.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Указывает, включен ли режим настройки для «цвет».|  
|`m_Color`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение. Содержит выбранный цвет.|  
|`m_ColorAutomatic`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение. Содержит цвет выбранного по умолчанию.|  
|`m_Colors`|Объект [CArray](../../mfc/reference/carray-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения. Содержит доступные цвета.|  
|`m_lstDocColors`|Объект [CList](../../mfc/reference/clist-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения. Содержит цвета текущего документа.|  
|`m_nColumns`|Значение типа integer. Содержит число столбцов для отображения в сетке цветов в меню выбора цвета.|  
|`m_pPalette`|Указатель на [CPalette](../../mfc/reference/cpalette-class.md). Содержит цвета, доступные в текущем меню выбора цвета.|  
|`m_pPopup`|Указатель на [CMFCColorPopupMenu класс](../../mfc/reference/cmfccolorpopupmenu-class.md) объекта. Меню выбора цвета, которое отображается при нажатии кнопки цвет.|  
|`m_strAutoColorText`|Строка. Метка кнопки «automatic» в меню выбора цвета.|  
|`m_strDocColorsText`|Строка. Метка кнопки в меню выбора цвета, которое отображает цвета документа.|  
|`m_strOtherText`|Строка. Метка кнопки «other» в меню выбора цвета.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию `CMFCColorButton` класс ведет себя как кнопки, которая открывает диалоговое окно выбора цвета. Диалоговое окно Выбор цветов содержит массив небольшой цвет кнопок и «other» кнопки, которая отображает пользовательские палитры. (Кнопка «other» обозначается стандартной системы **Дополнительные цвета**.) Когда пользователь выбирает новый цвет `CMFCColorButton` отражает изменение объекта и отображает выбранный цвет.  
  
 Создайте элемент управления button цвет непосредственно в коде или с помощью **ClassWizard** средство и шаблон диалогового окна. При создании элемента управления button цвет напрямую добавить `CMFCColorButton` переменных для приложений, а затем вызовите конструктор и `Create` методы `CMFCColorButton` объекта. При использовании **ClassWizard**, добавьте `CButton` переменной к приложению и измените тип переменной из `CButton` для `CMFCColorButton`.  
  
 Диалоговое окно Выбор цветов ( [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)) отображается по [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) метод, когда платформа вызывает `OnLButtonDown` обработчика событий. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) метод может быть переопределен для поддержки пользовательских цветов.  
  
 `CMFCColorButton` Объекта уведомляет его родителя, который цвет изменяется путем отправки их `WM_COMMAND | BN_CLICKED` уведомления. Родительский элемент использует [CMFCColorButton::GetColor](#getcolor) метод для извлечения текущего цвета.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить кнопку цвета с помощью различных методов в `CMFCColorButton` класса. Методы задания цвета, «цвет» и его число столбцов и включить автоматическое и другие кнопки. Данный пример является частью [состояние панели демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>  CMFCColorButton::CMFCColorButton  
 Создает новое `CMFCColorButton` объекта.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorButton::EnableAutomaticButton  
 Включить или отключить кнопки «automatic», элемент выбора цвета и задать цвет автоматически (по умолчанию).  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Задает текст, автоматической кнопки.  
  
 [in] `colorAutomatic`  
 RGB-значение, указывающее цвет автоматической кнопки по умолчанию.  
  
 [in] `bEnable`  
 Указывает, включен ли автоматической кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton  
 Включение и отключение «other» кнопки, которая показана ниже обычного цветного кнопок.  
  
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
 Указывает, является ли [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно или диалоговое окно Цвет системы открывается при нажатии кнопки.  
  
 [in] `bEnable`  
 Указывает, включен ли кнопки «other».  
  
### <a name="remarks"></a>Примечания  
 Нажмите кнопку «другие» для отображения диалоговое окно цвета. Если *bAltColorDlg* параметр `TRUE`, [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md) отображается; в противном случае отображается диалоговое окно Цвет системы.  
  
##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor  
 Получает текущий цвет автоматически (по умолчанию).  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение RGB, представляющее текущий автоматическое цвет.  
  
### <a name="remarks"></a>Примечания  
 Текущий цвет автоматической задается [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) метод.  
  
##  <a name="getcolor"></a>  CMFCColorButton::GetColor  
 Получает текущий выбранный цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme  
 Указывает, отображается ли кнопка текущего цвета в визуальном стиле Windows XP.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если визуальные стили поддерживаются и кнопкой текущий цвет отображается в визуальном стиле Windows XP; в противном случае `FALSE`.  
  
##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode  
 Задает цвет кнопки режим настройки.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Если вам нужно добавить кнопку цвета на странице диалогового окна настройки (или пользователи могут выбрать другие цвета во время настройки), необходимо включить кнопку, задав `m_bEnabledInCustomizeMode` члена `TRUE`. По умолчанию, этот член имеет значение `FALSE`.  
  
##  <a name="ondraw"></a>  CMFCColorButton::OnDraw  
 Вызывается платформой для отрисовки изображения кнопки.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, который используется для отображения изображения кнопки.  
  
 [in] `rect`  
 Прямоугольник, ограничивающий кнопки.  
  
 [in] `uiState`  
 Задает визуальное состояние кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для настройки процесса подготовки к просмотру.  
  
##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder  
 Вызывается платформой для отображения границы кнопки.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, используемого для рисования границ.  
  
 [in] `rectClient`  
 Прямоугольник в контексте устройства, который задается параметром `pDC` параметр, который определяет границы кнопки для отображения.  
  
 [in] `uiState`  
 Задает визуальное состояние кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки внешнего вида кнопка цвета границы.  
  
##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect  
 Вызывается платформой для отображения прямоугольник фокуса, когда кнопка имеет фокус.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, используемый для отрисовки прямоугольника фокуса.  
  
 [in] `rectClient`  
 Прямоугольник в контексте устройства, заданные `pDC` параметр, который определяет границы кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для настройки внешнего вида прямоугольника фокуса.  
  
##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup  
 Вызывается перед отображением всплывающей цветовой панели.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette  
 Инициализирует `m_pPalette` защищенные данные-члены указанного палитры или палитры системы по умолчанию.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pPal`|Указатель на логическую палитру или `NULL`. Если `NULL`, используется по умолчанию системной палитры.|  
  
##  <a name="setcolor"></a>  CMFCColorButton::SetColor  
 Задает цвет кнопки.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 RGB-значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName  
 Указывает имя цвета.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Значение цвета RGB.  
  
 [in] `strName`  
 Имя цвета.  
  
### <a name="remarks"></a>Примечания  
 Список названий цветов является глобальным каждого приложения. Следовательно, этот метод передает свои параметры в [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber  
 Определяет количество столбцов, отображаемых в таблице цветов, которые отображаются для пользователя во время процесса выбора цвета для пользователя.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nColumns`  
 Указывает количество столбцов.  
  
### <a name="remarks"></a>Примечания  
 Пользователь может выбрать цвет из всплывающей цветовой панели отображается таблица стандартных цветов. Используйте этот метод, чтобы определить количество столбцов в таблице.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors  
 Задает набор цветов и имя набора. Набор цветов, отображается с использованием [CMFCColorBar класс](../../mfc/reference/cmfccolorbar-class.md) объекта.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Метка отображается набор цветов документа.  
  
 [in] `lstColors`  
 Ссылка на список значений RGB.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCColorButton` объекта ведет список значений RGB, которые передаются [CMFCColorBar класс](../../mfc/reference/cmfccolorbar-class.md) объекта. При отображении цветовую шкалу, эти цвета отображаются в специальный раздел, метка которого определяется `lpszLabel` параметра.  
  
##  <a name="setpalette"></a>  CMFCColorButton::SetPalette  
 Задает стандартные цвета для отображения на всплывающей панели цветов.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPalette`  
 Указатель на цветовой палитры.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent  
 Изменение размера кнопки в соответствии с его текст и изображения.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCalcOnly`  
 Если значение ненулевое, новый размер элемента управления button вычисляется, но фактический размер не изменяется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` объект, который указывает новый размер элемента управления button.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor  
 Вызывается платформой, когда пользователь выбирает цвет из цветовой шкалы, отображаемый, когда пользователь нажимает кнопку цвета.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Цвет, выбранный пользователем.  
  
### <a name="remarks"></a>Примечания  
 `UpdateColor` Функция изменяет цвет выбранного кнопки и уведомляет родительской, отправляя `WM_COMMAND` сообщений с `BN_CLICKED` уведомлений standard. Используйте [CMFCColorButton::GetColor](#getcolor) метод для извлечения выбранного цвета.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)   
 [Класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette-класс](../../mfc/reference/cpalette-class.md)   
 [CArray-класс](../../mfc/reference/carray-class.md)   
 [CList-класс](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)
