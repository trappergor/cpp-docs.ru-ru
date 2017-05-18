---
title: "Класс CMFCButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
dev_langs:
- C++
helpviewer_keywords:
- CMFCButton::CreateObject method
- CMFCButton::DrawItem method
- CMFCButton::PreTranslateMessage method
- CMFCButton constructor
- CMFCButton::OnDrawParentBackground method
- CMFCButton class
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 89cd722ac15a1d9ac6b6c815c837559e302f0e68
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbutton-class"></a>Класс CMFCButton
`CMFCButton` Класс добавляет функциональные возможности для [CButton](../../mfc/reference/cbutton-class.md) класса, такие как выравнивание текста кнопки, объединение текста кнопки и изображения, выбор курсора и указание подсказки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Конструктор по умолчанию.|  
|`CMFCButton::~CMFCButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|Сбрасывает внутренние переменные и освобождает все ресурсы, выделенные как изображения, точечные рисунки и значки.|  
|`CMFCButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCButton::DrawItem`|Вызывается инфраструктурой при изменении внешнего вида кнопки пользователем. (Переопределяет [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Указывает, следует ли отображать полный текст всплывающей подсказки в окно всплывающей подсказки больших или усеченные версии текста в окне подсказки небольшой.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Указывает, является ли шрифт текста кнопки таким же, как шрифт меню приложения.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Указывает, соответствует ли стиль границы кнопки текущей темы Windows.|  
|`CMFCButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Возвращает ссылку на базовый элемент управления всплывающей подсказки.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Указывает, является ли флажок или переключатель автоматического кнопки.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Указывает, установлен ли кнопки режима auto-repeat.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Указывает, является ли кнопка кнопка флажка.|  
|[CMFCButton::IsChecked](#ischecked)|Указывает, установлен ли флажок текущей кнопки.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Указывает, выделяется ли кнопки.|  
|[CMFCButton::IsPressed](#ispressed)|Указывает, помещено, выделенной кнопки.|  
|[CMFCButton::IsPushed](#ispushed)|Указывает, является ли кнопка в нажатом состоянии.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Указывает, является ли кнопка переключателя.|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Указывает, соответствует ли стиль границы кнопки для текущей темы Windows.|  
|`CMFCButton::OnDrawParentBackground`|Рисует фон родительского объекта в заданной области. (Переопределяет [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Задает кнопку в режим автоматического повтора.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Задает изображение для нажатой кнопки.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Задает фоновый цвет текста кнопки.|  
|[CMFCButton::SetImage](#setimage)|Задает изображение для кнопки.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|Задает изображение курсора.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Задает курсор на изображение ладони.|  
|[CMFCButton::SetStdImage](#setstdimage)|Использует `CMenuImages` объекта, чтобы задать изображение кнопки.|  
|[CMFCButton::SetTextColor](#settextcolor)|Задает цвет текста кнопки для кнопки, которая не выбрана.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Задает цвет текста кнопки для выбранной кнопки.|  
|[CMFCButton::SetTooltip](#settooltip)|Связывает всплывающей подсказки с кнопкой.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Изменение размера кнопки содержать текст кнопки и изображения.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Вызывается платформой для отображения кнопки.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Вызывается платформой для рисования границы кнопки.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается платформой для отрисовки прямоугольника фокуса для кнопки.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Вызывается платформой для рисования текста кнопки.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Вызывается платформой для рисования фона текста кнопки.|  
|[CMFCButton::SelectFont](#selectfont)|Получает шрифт, который связан с помощью заданного контекста устройств.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Указывает, следует ли прямоугольник фокуса вокруг кнопки.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Указывает, следует ли выделять BS_CHECKBOX стиль кнопки при наведении курсора.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Указывает, следует ли отображать изображения справа от кнопки.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Указывает, является ли кнопки прозрачным.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Задает выравнивание текста кнопки.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Указывает стиль кнопки, например без рамки, плоскими точками плоского или 3D.|  
  
## <a name="remarks"></a>Примечания  
 Другие типы кнопок являются производными от `CMFCButton` класса, такие как [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) класс, который поддерживает гиперссылки, и `CMFCColorButton` класс, который поддерживает диалоговое окно выбора цвета.  
  
 Стиль `CMFCButton` объект может быть *3D*, *плоский*, *точками плоский* или *без границы*. Текст кнопки могут быть выровнены по слева, сверху или центр кнопки. Во время выполнения можно управлять, отображаются ли кнопки текст, изображения или текст и изображения. Можно также указать отображения изображения конкретного курсора при наведении курсора мыши на кнопку.  
  
 Создайте элемент управления button, непосредственно в коде или с помощью **мастер классов MFC** средство и шаблон диалогового окна. При создании элемента управления button в непосредственно добавить `CMFCButton` переменных для вашего приложения, а затем вызвать конструктор и `Create` методы `CMFCButton` объекта. При использовании **мастер классов MFC**, добавьте `CButton` переменных для вашего приложения и измените тип переменной из `CButton` в `CMFCButton`.  
  
 Для обработки сообщений уведомления в приложении поле диалогового окна необходимо добавьте запись сопоставления сообщений и обработчика событий для каждого уведомления. Уведомления, отправляемые по `CMFCButton` являются такими же, как отправленные `CButton` объекта.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить свойства кнопки с помощью различных методов в `CMFCButton` класса. Пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#31;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#32;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#33;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbutton.h  
  
##  <a name="cleanup"></a>CMFCButton::CleanUp  
 Сбрасывает внутренние переменные и освобождает все ресурсы, выделенные как изображения, точечные рисунки и значки.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>CMFCButton::EnableFullTextTooltip  
 Указывает, следует ли отображать полный текст всплывающей подсказки в окно всплывающей подсказки больших или усеченные версии текста в окне подсказки небольшой.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bOn`  
 `TRUE`Чтобы отобразить весь текст; `FALSE` для отображения усечение текста.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablemenufont"></a>CMFCButton::EnableMenuFont  
 Указывает, является ли шрифт текста кнопки таким же, как шрифт меню приложения.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bOn`  
 `TRUE`использовать шрифт меню приложения в качестве шрифта текста кнопки; `FALSE` для использования системного шрифта. Значение по умолчанию — `TRUE`.  
  
 [in] `bRedraw`  
 `TRUE`Чтобы немедленно обновить экран; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если не использовать этот метод для задания шрифта текста кнопки, можно указать шрифт с [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) метод. Если не указать шрифт вообще, платформа задает шрифт по умолчанию.  
  
##  <a name="enablewindowstheming"></a>CMFCButton::EnableWindowsTheming  
 Указывает, соответствует ли стиль границы кнопки текущей темы Windows.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Использование текущей темы Windows для рисования границы кнопки; `FALSE` не использовать темы Windows. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод влияет на все кнопки в приложении, которые являются производными от `CMFCButton` класса.  
  
##  <a name="gettooltipctrl"></a>CMFCButton::GetToolTipCtrl  
 Возвращает ссылку на базовый элемент управления всплывающей подсказки.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на базовый элемент управления всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isautocheck"></a>CMFCButton::IsAutoCheck  
 Указывает, является ли флажок или переключатель автоматического кнопки.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка имеет стиль BS_AUTOCHECKBOX или BS_AUTORADIOBUTTON; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isautorepeatcommandmode"></a>CMFCButton::IsAutorepeatCommandMode  
 Указывает, установлен ли кнопки режима auto-repeat.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопки устанавливается режим автоматического повтора; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCButton::SetAutorepeatMode](#setautorepeatmode) метод для установки кнопки в режим автоматического повтора.  
  
##  <a name="ischeckbox"></a>CMFCButton::IsCheckBox  
 Указывает, является ли кнопка кнопка флажка.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопка имеет стиль BS_CHECKBOX или BS_AUTOCHECKBOX; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ischecked"></a>CMFCButton::IsChecked  
 Указывает, установлен ли флажок текущей кнопки.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если установлен флажок текущей кнопки; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Инфраструктура использует различные способы указания проверки различных видов кнопок. Например переключателя, если он содержит точку; флажок установлен, если он содержит **X**.  
  
##  <a name="ishighlighted"></a>CMFCButton::IsHighlighted  
 Указывает, выделяется ли кнопки.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопка выделена; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Кнопка выделяется при наведении указателя мыши на кнопку.  
  
##  <a name="ispressed"></a>CMFCButton::IsPressed  
 Указывает, помещено, выделенной кнопки.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если нажата кнопка; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ispushed"></a>CMFCButton::IsPushed  
 Указывает, является ли кнопка в нажатом состоянии.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопки помещается; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isradiobutton"></a>CMFCButton::IsRadioButton  
 Указывает, является ли кнопка переключателя.  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если стиль кнопки BS_RADIOBUTTON или BS_AUTORADIOBUTTON; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="iswindowsthemingenabled"></a>CMFCButton::IsWindowsThemingEnabled  
 Указывает, соответствует ли стиль границы кнопки для текущей темы Windows.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если стиль границы кнопки соответствует текущей темы Windows; в противном случае — `FALSE`.  
  
##  <a name="m_bdrawfocus"></a>CMFCButton::m_bDrawFocus  
 Указывает, следует ли прямоугольник фокуса вокруг кнопки.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте `m_bDrawFocus` члена `TRUE` framework нарисовать прямоугольник фокуса вокруг текста кнопки и изображения, если кнопка получает фокус.  
  
 `CMFCButton` Конструктор инициализирует этот элемент для `TRUE`.  
  
##  <a name="m_bhighlightchecked"></a>CMFCButton::m_bHighlightChecked  
 Указывает, следует ли выделять BS_CHECKBOX стиль кнопки при наведении курсора.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте `m_bHighlightChecked` члена `TRUE` для указания, что платформа выделите BS_CHECKBOX стиль кнопки, при наведении указателя мыши.  
  
##  <a name="m_brightimage"></a>CMFCButton::m_bRightImage  
 Указывает, следует ли отображать изображения справа от кнопки.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте `m_bRightImage` члена `TRUE` для указания, что платформа будет отображаться изображение кнопки справа от кнопки текстовую метку.  
  
##  <a name="m_btransparent"></a>CMFCButton::m_bTransparent  
 Указывает, является ли кнопки прозрачным.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте `m_bTransparent` члена `TRUE` для указания, что платформа будет прозрачности кнопки. `CMFCButton` Конструктор инициализирует этот элемент для `FALSE`.  
  
##  <a name="m_nalignstyle"></a>CMFCButton::m_nAlignStyle  
 Задает выравнивание текста кнопки.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте один из следующих `CMFCButton::AlignStyle` значений перечисления, чтобы задать выравнивание текста кнопки:  
  
|Значение|Описание|  
|-----------|-----------------|  
|ALIGN_CENTER|(По умолчанию) Выравнивание текста кнопки в центре кнопки.|  
|ALIGN_LEFT|Кнопка текст выравнивается по левой кнопки.|  
|ALIGN_RIGHT|Кнопка текст выравнивается по правой части кнопки.|  
  
 `CMFCButton` Конструктор инициализирует этот элемент для ALIGN_CENTER.  
  
##  <a name="m_nflatstyle"></a>CMFCButton::m_nFlatStyle  
 Указывает стиль кнопки, например без рамки, плоскими точками плоского или 3D.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице перечислены `CMFCButton::m_nFlatStyle` значений перечисления, определяющих внешний вид кнопки.  
  
|Значение|Описание|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(По умолчанию) Кнопка для высокого уровня, трехмерный сторонами. При нажатии кнопки, кнопка нажатия клавиши в глубокой отступа.|  
|BUTTONSTYLE_FLAT|Когда указатель мыши не наведите на кнопку, кнопки кажется двухмерной и не имеет вызванного сторон. При наведении указателя мыши на кнопку, кнопка появляется низкий, трехмерный сторонами. При нажатии кнопки, кнопка нажатия клавиши в неполную отступа.|  
|BUTTONSTYLE_SEMIFLAT|Кнопка появляется на низкий, трехмерный сторонами. При нажатии кнопки, кнопка нажатия клавиши в глубокой отступа.|  
|BUTTONSTYLE_NOBORDERS|Кнопка не вызвало сторон и всегда отображается двухмерный. Нажатие в отступ при нажатии кнопка не отображается.|  
  
 `CMFCButton` Конструктор инициализирует этот элемент для `BUTTONSTYLE_3D`.  
  
### <a name="example"></a>Пример  
 Ниже приведен пример, как задать значения `m_nFlatStyle` переменной-члена в `CMFCButton` класса. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#29;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>CMFCButton::OnDraw  
 Вызывается платформой для отображения кнопки.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
 [in] `uiState`  
 Текущее состояние кнопки. Дополнительные сведения см. в разделе `itemState` членом [структура DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) раздела.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для отображения кнопки.  
  
##  <a name="ondrawborder"></a>CMFCButton::OnDrawBorder  
 Вызывается платформой для рисования границы кнопки.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectClient`  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
 [in] `uiState`  
 Текущее состояние кнопки. Дополнительные сведения см. в разделе `itemState` членом [структура DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) раздела.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для рисования границы.  
  
##  <a name="ondrawfocusrect"></a>CMFCButton::OnDrawFocusRect  
 Вызывается платформой для отрисовки прямоугольника фокуса для кнопки.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectClient`  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для отрисовки прямоугольника фокуса.  
  
##  <a name="ondrawtext"></a>CMFCButton::OnDrawText  
 Вызывается платформой для рисования текста кнопки.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
 [in] `strText`  
 Текст для отрисовки.  
  
 [in] `uiDTFlags`  
 Флаги, определяющие способ форматирования текста. Дополнительные сведения см. в разделе `nFormat` параметр [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) метод.  
  
 [in] `uiState`  
 (Зарезервировано).  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для рисования текста кнопки.  
  
##  <a name="onfillbackground"></a>CMFCButton::OnFillBackground  
 Вызывается платформой для рисования фона текста кнопки.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectClient`  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для рисования фона кнопки.  
  
##  <a name="selectfont"></a>CMFCButton::SelectFont  
 Получает шрифт, который связан с помощью заданного контекста устройств.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Переопределите этот метод, чтобы использовать собственный код для получения шрифта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setautorepeatmode"></a>CMFCButton::SetAutorepeatMode  
 Задает кнопку в режим автоматического повтора.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTimeDelay`  
 Неотрицательное число, задающее интервал между сообщения, отправленные родительского окна. Интервал измеряется в миллисекундах, и значение по умолчанию — 500 миллисекунд. Укажите ноль, чтобы отключить режим auto-repeat сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод приводит к постоянно отправлять сообщения WM_COMMAND родительского окна до освобождения кнопки, кнопки или `nTimeDelay` параметра равным нулю.  
  
##  <a name="setcheckedimage"></a>CMFCButton::SetCheckedImage  
 Задает изображение для нажатой кнопки.  
  
```  
void SetCheckedImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetCheckedImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetCheckedImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hIcon`  
 Дескриптор для значка, который содержит растровое изображение и маску для нового образа.  
  
 [in] `bAutoDestroy`  
 `TRUE`Чтобы указать, что точечный рисунок ресурсы будут уничтожены автоматически; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] `hIconHot`  
 Дескриптор для значка, который содержит изображения для выбранного состояния.  
  
 [in] `hBitmap`  
 Дескриптор точечного рисунка, содержащий образ для невыбранных состояния.  
  
 [in] `hBitmapHot`  
 Дескриптор точечного рисунка, содержащий образ для выбранного состояния.  
  
 [in] `bMap3dColors`  
 Указывает прозрачный цвет фона кнопки; то есть поверхность кнопки. `TRUE`Чтобы использовать значение цвета RGB (192, 192, 192); `FALSE` использовать значение цвета определяется `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `uiBmpResId`  
 Идентификатор ресурса для невыбранных изображения.  
  
 [in] `uiBmpHotResId`  
 Идентификатор ресурса для выбранного изображения.  
  
 [in] `hIconDisabled`  
 Дескриптор значок отключенного рисунка.  
  
 [in] `hBitmapDisabled`  
 Дескриптор точечного рисунка, содержащий отключенного рисунка.  
  
 [in] `uiBmpDsblResID`  
 Идентификатор ресурса растрового изображения отключено.  
  
 [in] `bAlphaBlend`  
 `TRUE`для использования только 32-разрядные изображения, использующие альфа-канал; `FALSE`, чтобы не использовать только образы альфа-канала. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfacecolor"></a>CMFCButton::SetFaceColor  
 Задает фоновый цвет текста кнопки.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `crFace`  
 Значение цвета RGB.  
  
 [in] `bRedraw`  
 `TRUE`Чтобы обновить экран немедленно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить новый цвет заливки фона кнопки (лицевой стороной). Обратите внимание, что фон не будет заполнен при [CMFCButton::m_bTransparent](#m_btransparent) является переменной-члена `TRUE`.  
  
##  <a name="setimage"></a>CMFCButton::SetImage  
 Задает изображение для кнопки.  
  
```  
void SetImage(
    HICON hIcon,  
    BOOL bAutoDestroy=TRUE,  
    HICON hIconHot=NULL,  
    HICON hIconDisabled=NULL,  
    BOOL bAlphaBlend=FALSE);

 
void SetImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy=TRUE,  
    HBITMAP hBitmapHot=NULL,  
    BOOL bMap3dColors=TRUE,  
    HBITMAP hBitmapDisabled=NULL);

 
void SetImage(
    UINT uiBmpResId,  
    UINT uiBmpHotResId=0,  
    UINT uiBmpDsblResID=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hIcon`  
 Дескриптор для значка, который содержит растровое изображение и маску для нового образа.  
  
 [in] `bAutoDestroy`  
 `TRUE`Чтобы указать, что точечный рисунок ресурсы будут уничтожены автоматически; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] `hIconHot`  
 Дескриптор для значка, который содержит изображения для выбранного состояния.  
  
 [in] `hBitmap`  
 Дескриптор точечного рисунка, содержащий образ для невыбранных состояния.  
  
 [in] `hBitmapHot`  
 Дескриптор точечного рисунка, содержащий образ для выбранного состояния.  
  
 [in] `uiBmpResId`  
 Идентификатор ресурса для невыбранных изображения.  
  
 [in] `uiBmpHotResId`  
 Идентификатор ресурса для выбранного изображения.  
  
 [in] `bMap3dColors`  
 Указывает прозрачный цвет фона кнопки; то есть поверхность кнопки. `TRUE`Чтобы использовать значение цвета RGB (192, 192, 192); `FALSE` использовать значение цвета определяется `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `hIconDisabled`  
 Дескриптор значок отключенного рисунка.  
  
 [in] `hBitmapDisabled`  
 Дескриптор точечного рисунка, содержащий отключенного рисунка.  
  
 [in] `uiBmpDsblResID`  
 Идентификатор ресурса растрового изображения отключено.  
  
 [in] `bAlphaBlend`  
 `TRUE`для использования только 32-разрядные изображения, использующие альфа-канал; `FALSE`, чтобы не использовать только образы альфа-канала. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных версий `SetImage` метод `CMFCButton` класса. Пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#31;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>CMFCButton::SetMouseCursor  
 Задает изображение курсора.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hcursor`  
 Дескриптор курсора.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы связать изображение курсора, например курсор в виде руки, с помощью кнопки. Курсор загружается из ресурсов приложения.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetMouseCursor` метод `CMFCButton` класса. Пример является частью кода в [образец новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#28;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#30;](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>CMFCButton::SetMouseCursorHand  
 Задает курсор на изображение ладони.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы связать изображение курсора руки с помощью кнопки. Курсор загружается из ресурсов приложения.  
  
##  <a name="setstdimage"></a>CMFCButton::SetStdImage  
 Использует `CMenuImages` объекта, чтобы задать изображение кнопки.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `id`  
 Один из идентификаторов изображение кнопки, определенные в `CMenuImage::IMAGES_IDS` перечисления. Изображения, например стрелки, контакты и переключатели определенные значения изображения.  
  
 [in] `state`  
 Один из идентификаторов состояние кнопки изображения, определенные в `CMenuImages::IMAGE_STATE` перечисления. Изображение состояния укажите кнопку цвета, например черный, серые, светло-серый белый и темно-серый. Значение по умолчанию — `CMenuImages::ImageBlack`.  
  
 [in] `idDisabled`  
 Один из идентификаторов изображение кнопки, определенные в `CMenuImage::IMAGES_IDS` перечисления. Изображение показывает, что кнопка отключена. Значение по умолчанию — первое изображение кнопки ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settextcolor"></a>CMFCButton::SetTextColor  
 Задает цвет текста кнопки для кнопки, которая не выбрана.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrText`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settexthotcolor"></a>CMFCButton::SetTextHotColor  
 Задает цвет текста кнопки для выбранной кнопки.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrTextHot`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settooltip"></a>CMFCButton::SetTooltip  
 Связывает всплывающей подсказки с кнопкой.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszToolTipText`  
 Указатель на текст всплывающей подсказки. Укажите NULL, чтобы отключить подсказки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizetocontent"></a>CMFCButton::SizeToContent  
 Изменение размера кнопки содержать текст кнопки и изображения.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCalcOnly`  
 `TRUE`вычисления, но не изменять, новый размер кнопки. `FALSE` изменение размера кнопки. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` , содержащий новый размер кнопки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вычисляет новый размер, включающий поля по горизонтали 10 пикселей и вертикальное поле 5 пикселей.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)   
 [Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)   
 [Класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

