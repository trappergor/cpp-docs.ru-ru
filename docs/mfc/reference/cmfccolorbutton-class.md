---
title: "Класс CMFCColorButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton::m_Color data member
- CMFCColorButton::m_bAutoSetFocus data member
- CMFCColorButton::m_pPopup data member
- CMFCColorButton::m_nColumns data member
- CMFCColorButton class
- CMFCColorButton::m_strAutoColorText data member
- CMFCColorButton::m_bAltColorDlg data member
- CMFCColorButton::m_strDocColorsText data member
- CMFCColorButton::m_strOtherText data member
- CMFCColorButton::m_pPalette data member
- CMFCColorButton::m_lstDocColors data member
- CMFCColorButton::m_ColorAutomatic data member
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
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
ms.openlocfilehash: 6a9290d396c8ce5ccafa2ae556b21ff89806d830
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbutton-class"></a>Класс CMFCColorButton
`CMFCColorButton` И [CMFCColorBar класса](../../mfc/reference/cmfccolorbar-class.md) классы используются совместно, чтобы реализовать управление палитрой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Создает новый `CMFCColorButton` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Включает и отключает кнопка «автоматический», расположенный выше регулярного цветные кнопки. (Кнопка автоматического стандартной системе обозначается **автоматическое**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Включает и отключает «other» кнопки, расположенные ниже регулярных цветные кнопки. (Стандартная система имеет метку «other» кнопку **Дополнительные цвета... **.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Получает текущий автоматическое цвет.|  
|[CMFCColorButton::GetColor](#getcolor)|Получает цвет кнопки.|  
|[CMFCColorButton::SetColor](#setcolor)|Задает цвет кнопки.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Задает имя цвета.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов в диалоговом окне выбора цвета.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Задает список цветов конкретного документа, которые отображаются в диалоговом окне выбора цвета.|  
|[CMFCColorButton::SetPalette](#setpalette)|Палитра цветов стандартный.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Изменение размера кнопки в зависимости от его размера, текста и изображений.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Указывает, отображается ли кнопка текущего цвета в визуальный стиль Windows XP.|  
|[CMFCColorButton::OnDraw](#ondraw)|Вызывается платформой для отображения изображения кнопки.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Вызывается платформой для отображения границы кнопки.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается платформой для отображения прямоугольника фокуса, когда кнопка имеет фокус.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Вызывается инфраструктурой при отображения диалогового окна выбора цвета.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Инициализирует `m_pPalette` защищенный член данных заданного палитру или палитры системы по умолчанию.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Вызывается платформой, когда пользователь выбирает цвет в палитре диалогового окна выбора цвета.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|`m_bAltColorDlg`|Логическое значение. Если `TRUE`, отображает платформа [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) цвет диалоговым окном, когда *других* кнопки, или если `FALSE`, диалоговое окно Цвет системы. Значение по умолчанию — `TRUE`. Дополнительные сведения см. в разделе [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Логическое значение. Если `TRUE`, платформа устанавливает фокус на меню «Цвет» при отображении меню или `FALSE`, не изменяет фокус. Значение по умолчанию — `TRUE`.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Указывает, включен ли режим настройки для «цвет».|  
|`m_Color`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение. Содержит выбранный цвет.|  
|`m_ColorAutomatic`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение. Содержит цвет выбранных по умолчанию.|  
|`m_Colors`|Объект [CArray](../../mfc/reference/carray-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения. Содержит доступные цвета.|  
|`m_lstDocColors`|Объект [CList](../../mfc/reference/clist-class.md) из [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значения. Содержит цвета текущего документа.|  
|`m_nColumns`|Значение типа integer. Содержит число столбцов для отображения в сетке цветов в меню выбора цвета.|  
|`m_pPalette`|Указатель на [CPalette](../../mfc/reference/cpalette-class.md). Содержит цвета, которые доступны в меню выбора цвета.|  
|`m_pPopup`|Указатель на [CMFCColorPopupMenu класс](../../mfc/reference/cmfccolorpopupmenu-class.md) объекта. Меню выбора цвета, которое отображается при нажатии кнопки цвет.|  
|`m_strAutoColorText`|Строка. Метка кнопки «автоматический» в меню выбора цвета.|  
|`m_strDocColorsText`|Строка. Название кнопки в меню выбора цвета, который отображает цвета документа.|  
|`m_strOtherText`|Строка. Метка кнопки «other» в меню выбора цвета.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию `CMFCColorButton` класс ведет себя как кнопка, которая открывает диалоговое окно выбора цвета. Диалоговое окно Выбор цветов содержит массив небольшие цветные кнопки и «other» кнопку, которая отображает пользовательские палитры. (Стандартная система имеет метку «other» кнопку **Дополнительные цвета... **.) Когда пользователь выбирает новый цвет `CMFCColorButton` отражает изменение объекта и отображает выбранный цвет.  
  
 Создайте элемент управления button цвет непосредственно в коде или с помощью **ClassWizard** средство и шаблон диалогового окна. При создании элемента управления button цвет непосредственно добавить `CMFCColorButton` переменной для вашего приложения, а затем вызвать конструктор и `Create` методы `CMFCColorButton` объекта. При использовании **ClassWizard**, добавьте `CButton` переменных для вашего приложения и измените тип переменной из `CButton` в `CMFCColorButton`.  
  
 Диалоговое окно выбора цвета ( [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)) отображается по [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) когда платформа вызывает метод `OnLButtonDown` обработчика событий. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) метод может быть переопределен для поддержки пользовательский цвет выделения.  
  
 `CMFCColorButton` Объекта уведомляет его родителя, который меняет цвет, отправив `WM_COMMAND | BN_CLICKED` уведомления. Родительский элемент использует [CMFCColorButton::GetColor](#getcolor) метод для извлечения текущего цвета.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить кнопку цвета, используя различные методы в `CMFCColorButton` класса. Методы цвета «цвет» и его число столбцов и включить автоматическое и другие кнопки. Этот пример является частью [демонстрационного панель состояния](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#10;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&11;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolorbutton.h  
  
##  <a name="a-namecmfccolorbuttona--cmfccolorbuttoncmfccolorbutton"></a><a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton  
 Создает новый `CMFCColorButton` объекта.  
  
```  
CMFCColorButton();
```  
  
##  <a name="a-nameenableautomaticbuttona--cmfccolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton  
 Включить или отключить кнопки «автоматический» элемент выбора цвета и задайте цвет автоматически (по умолчанию).  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Задает текст кнопки автоматический.  
  
 [in] `colorAutomatic`  
 RGB-значение, указывающее цвет по умолчанию автоматическое кнопки.  
  
 [in] `bEnable`  
 Указывает, включена ли автоматическая кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenableotherbuttona--cmfccolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton  
 Включение или отключение кнопки «other», которая расположена под обычные цветные кнопки.  
  
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
 Нажмите кнопку «другие», чтобы отобразить диалоговое окно. Если *bAltColorDlg* параметр `TRUE`, [CMFCColorDialog класса](../../mfc/reference/cmfccolordialog-class.md) отображается; в противном случае — отображается диалоговое окно Цвет системы.  
  
##  <a name="a-namegetautomaticcolora--cmfccolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor  
 Получает текущий цвет автоматически (по умолчанию).  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение RGB, представляющее текущий автоматическое цвет.  
  
### <a name="remarks"></a>Примечания  
 Задается автоматическое текущий цвет [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) метод.  
  
##  <a name="a-namegetcolora--cmfccolorbuttongetcolor"></a><a name="getcolor"></a>CMFCColorButton::GetColor  
 Получает текущий выбранный цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdrawxpthemea--cmfccolorbuttonisdrawxptheme"></a><a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme  
 Указывает, отображается ли кнопка текущего цвета в визуальный стиль Windows XP.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если визуальные стили поддерживаются и кнопкой текущий цвет отображается в визуальный стиль Windows XP; в противном случае — `FALSE`.  
  
##  <a name="a-namembenabledincustomizemodea--cmfccolorbuttonmbenabledincustomizemode"></a><a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode  
 Задает цвет кнопки режим настройки.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Если требуется добавить кнопку цвета в диалоговом окне настройки страницы (или разрешить пользователю выбрать другую цвет во время настройки), включить кнопку, задав `m_bEnabledInCustomizeMode` члена `TRUE`. По умолчанию этот член имеет значение `FALSE`.  
  
##  <a name="a-nameondrawa--cmfccolorbuttonondraw"></a><a name="ondraw"></a>CMFCColorButton::OnDraw  
 Вызывается платформой для визуализации изображения кнопки.  
  
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
  
##  <a name="a-nameondrawbordera--cmfccolorbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder  
 Вызывается платформой для отображения границы кнопки.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, используемый для рисования границы.  
  
 [in] `rectClient`  
 Прямоугольник, в контекст устройства, который задается параметром `pDC` параметр, который определяет границы кнопки для отображения.  
  
 [in] `uiState`  
 Задает визуальное состояние кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки внешнего вида кнопки цвет границы.  
  
##  <a name="a-nameondrawfocusrecta--cmfccolorbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect  
 Вызывается платформой для отображения прямоугольника фокуса, когда кнопка имеет фокус.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, используемый для отрисовки прямоугольника фокуса.  
  
 [in] `rectClient`  
 Прямоугольник, в контекст устройства, заданные `pDC` параметр, который определяет границы кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для настройки внешнего вида прямоугольника фокуса.  
  
##  <a name="a-nameonshowcolorpopupa--cmfccolorbuttononshowcolorpopup"></a><a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup  
 Вызывается перед отображением контекстного меню цветовой шкалы.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namerebuildpalettea--cmfccolorbuttonrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette  
 Инициализирует `m_pPalette` защищенный член данных заданного палитру или палитры системы по умолчанию.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pPal`|Указатель на логический палитру или `NULL`. Если `NULL`, используется палитра системы по умолчанию.|  
  
##  <a name="a-namesetcolora--cmfccolorbuttonsetcolor"></a><a name="setcolor"></a>CMFCColorButton::SetColor  
 Задает цвет кнопки.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 RGB-значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetcolornamea--cmfccolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFCColorButton::SetColorName  
 Задает имя цвета.  
  
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
 Список названий цветов глобальными для каждого приложения. Следовательно, этот метод передает свои параметры в [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="a-namesetcolumnsnumbera--cmfccolorbuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber  
 Определяет количество столбцов, отображаемых в таблице цветов, которые отображаются для пользователя, в процессе выбора цвета пользователя.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nColumns`  
 Указывает количество столбцов.  
  
### <a name="remarks"></a>Примечания  
 Пользователь может выбрать цвет из всплывающего окна цветовую шкалу, отображающей таблицу стандартных цветов. Используйте этот метод, чтобы определить количество столбцов в таблице.  
  
##  <a name="a-namesetdocumentcolorsa--cmfccolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors  
 Задает набор цветов и имя набора. Набор цветов, отображается с использованием [CMFCColorBar класс](../../mfc/reference/cmfccolorbar-class.md) объекта.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Задает метку для отображения с набором цвета документа.  
  
 [in] `lstColors`  
 Ссылка на список значений RGB.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCColorButton` объект ведет список RGB-значения, которые передаются [CMFCColorBar класс](../../mfc/reference/cmfccolorbar-class.md) объекта. При отображении цветовую шкалу эти цвета отображаются в специальном разделе, метка которого определяется `lpszLabel` параметр.  
  
##  <a name="a-namesetpalettea--cmfccolorbuttonsetpalette"></a><a name="setpalette"></a>CMFCColorButton::SetPalette  
 Задает стандартные цвета для отображения на цветовой шкале всплывающего окна.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPalette`  
 Указатель на цветовой палитры.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesizetocontenta--cmfccolorbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCColorButton::SizeToContent  
 Изменение размера кнопки в соответствии с его текст и изображения.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCalcOnly`  
 Если значение ненулевое, вычисляется новый размер элемента управления button, но фактический размер не изменяется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` объект, который указывает новый размер элемента управления кнопки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameupdatecolora--cmfccolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFCColorButton::UpdateColor  
 Вызывается платформой, когда пользователь выбирает цвет из цветовой полосы, которая отображается, когда пользователь нажимает кнопку цвет.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Цвет, выбранный пользователем.  
  
### <a name="remarks"></a>Примечания  
 `UpdateColor` Функция изменяет цвет выбранного кнопки и уведомляет родительским путем отправки `WM_COMMAND` сообщений с `BN_CLICKED` стандартное уведомление. Используйте [CMFCColorButton::GetColor](#getcolor) метод для извлечения выбранного цвета.  
  
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

