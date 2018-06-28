---
title: Класс CMFCButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd30c9f27d83e7d4cfaf9b993b258b069f73dc4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039236"
---
# <a name="cmfcbutton-class"></a>Класс CMFCButton
`CMFCButton` Класс расширяет его функциональные возможности [CButton](../../mfc/reference/cbutton-class.md) класса, такие как выравнивание текста кнопки, объединение текста кнопки и изображения, выбор курсора и указание подсказки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Конструктор по умолчанию.|  
|`CMFCButton::~CMFCButton`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|Сбрасывает внутренние переменные и освобождает ресурсы, выделенные как изображения, точечные рисунки и значки.|  
|`CMFCButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCButton::DrawItem`|Вызывается платформой при изменении внешнего вида кнопки владельцем. (Переопределяет [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Указывает, следует ли отображать полный текст всплывающей подсказки в окно всплывающей подсказки больших или усеченный версии текста в окне небольшой всплывающей подсказки.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Указывает, является ли шрифт текста кнопки таким же, как шрифт меню приложения.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Указывает, соответствует ли стиль границы кнопки текущей темы Windows.|  
|`CMFCButton::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Возвращает ссылку на базовый элемент управления всплывающей подсказки.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Указывает, является ли флажок или переключатель автоматической кнопки.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Указывает, устанавливается ли кнопка режим автоматического повтора.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Указывает, является ли кнопка флажок.|  
|[CMFCButton::IsChecked](#ischecked)|Указывает, установлен ли флажок текущей кнопки.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Указывает, выделяется ли кнопка.|  
|[CMFCButton::IsPressed](#ispressed)|Указывает ли кнопка помещается и выделен.|  
|[CMFCButton::IsPushed](#ispushed)|Указывает, является ли кнопка в нажатом состоянии.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Указывает, является ли кнопка типа "переключатель".|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Указывает, соответствует ли стиль границы кнопки текущей темы Windows.|  
|`CMFCButton::OnDrawParentBackground`|Рисует фон родительского объекта в заданной области. (Переопределяет [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Задает кнопку в режим автоматического повтора.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Задает изображение для нажатой кнопки.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Задает цвет фона для текста кнопки.|  
|[CMFCButton::SetImage](#setimage)|Задает изображение для кнопки.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|Задает изображение курсора.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Задает курсор на изображение ладони.|  
|[CMFCButton::SetStdImage](#setstdimage)|Использует `CMenuImages` объекта, чтобы задать значок кнопки.|  
|[CMFCButton::SetTextColor](#settextcolor)|Задает цвет текста кнопки для кнопки, не установлен.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Задает цвет текста кнопки для кнопки, которая выбрана.|  
|[CMFCButton::SetTooltip](#settooltip)|Связывает всплывающей подсказки с кнопкой.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Изменение размера кнопки для хранения его текст кнопки и изображения.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Вызывается платформой для отображения кнопки.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Вызывается платформой для рисования границы кнопки.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Вызывается платформой для отрисовки прямоугольника фокуса для кнопки.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Вызывается платформой для отрисовки текста кнопки.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Вызывается платформой при рисовании фона текста кнопки.|  
|[CMFCButton::SelectFont](#selectfont)|Возвращает шрифт, который связан с помощью заданного контекста устройств.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Указывает, следует ли прямоугольник фокуса вокруг кнопки.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Указывает, следует ли выделять BS_CHECKBOX стиль кнопки при наведении курсора.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Указывает, следует ли отображать изображение справа от кнопки.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Указывает, является ли кнопки прозрачным.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Задает выравнивание текста кнопки.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Указывает стиль кнопки, например без рамки, плоский, с плоской или объемные эффекты.|  
  
## <a name="remarks"></a>Примечания  
 Другие типы кнопок являются производными от `CMFCButton` класса, такие как [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) класса, поддерживающего гиперссылки и `CMFCColorButton` класса, поддерживающего диалоговое окно выбора цвета.  
  
 Стиль `CMFCButton` объект может быть *3D*, *плоский*, *с плоскими* или *без границы*. Текст кнопки могут быть выровнены по left, top или центр кнопки. Во время выполнения можно управлять, отображаются ли кнопки текст, изображения или текст и изображения. Можно также указать отображения изображения конкретного курсора при наведении курсора на кнопку.  
  
 Создайте элемент управления button непосредственно в коде или с помощью **мастер классов MFC** средство и шаблон диалогового окна. При создании элемента управления button напрямую добавить `CMFCButton` переменных для приложений, а затем вызовите конструктор и `Create` методы `CMFCButton` объекта. При использовании **мастер классов MFC**, добавьте `CButton` переменной к приложению и измените тип переменной из `CButton` для `CMFCButton`.  
  
 Для обработки сообщений уведомления в приложении поле диалогового окна необходимо добавьте запись сопоставления сообщений и обработчика событий для каждого уведомления. Уведомлений, отправляемых `CMFCButton` объекта используются те же отправленных `CButton` объекта.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить свойства кнопки с помощью различных методов `CMFCButton` класса. Пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbutton.h  
  
##  <a name="cleanup"></a>  CMFCButton::CleanUp  
 Сбрасывает внутренние переменные и освобождает ресурсы, выделенные как изображения, точечные рисунки и значки.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>  CMFCButton::EnableFullTextTooltip  
 Указывает, следует ли отображать полный текст всплывающей подсказки в окно всплывающей подсказки больших или усеченный версии текста в окне небольшой всплывающей подсказки.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bВ системах*  
 `TRUE` Чтобы отобразить весь текст; `FALSE` усечение отображения текста.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablemenufont"></a>  CMFCButton::EnableMenuFont  
 Указывает, является ли шрифт текста кнопки таким же, как шрифт меню приложения.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bВ системах*  
 `TRUE` Чтобы использовать шрифт меню приложения в качестве шрифта текста кнопки; `FALSE` использовать системный шрифт. Значение по умолчанию — `TRUE`.  
  
 [in] *bRedraw*  
 `TRUE` Чтобы немедленно обновить экран; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если не используется этот метод для задания шрифта текста кнопки, можно указать шрифт с [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) метод. Если не указать шрифт вообще, платформа задает шрифт по умолчанию.  
  
##  <a name="enablewindowstheming"></a>  CMFCButton::EnableWindowsTheming  
 Указывает, соответствует ли стиль границы кнопки текущей темы Windows.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 `TRUE` для использования текущей темы Windows для рисования границ кнопки; `FALSE` не использует тему. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод влияет на все кнопки в приложения, которые являются производными от `CMFCButton` класса.  
  
##  <a name="gettooltipctrl"></a>  CMFCButton::GetToolTipCtrl  
 Возвращает ссылку на базовый элемент управления всплывающей подсказки.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на базовый элемент управления всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isautocheck"></a>  CMFCButton::IsAutoCheck  
 Указывает, является ли флажок или переключатель автоматической кнопки.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если кнопка имеет стиль BS_AUTOCHECKBOX или BS_AUTORADIOBUTTON; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isautorepeatcommandmode"></a>  CMFCButton::IsAutorepeatCommandMode  
 Указывает, устанавливается ли кнопка режим автоматического повтора.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопке устанавливается в режим автоматического повтора. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCButton::SetAutorepeatMode](#setautorepeatmode) метод Установка кнопки режима автоматического повтора.  
  
##  <a name="ischeckbox"></a>  CMFCButton::IsCheckBox  
 Указывает, является ли кнопка флажок.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если эта кнопка имеет стиль BS_CHECKBOX или BS_AUTOCHECKBOX; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ischecked"></a>  CMFCButton::IsChecked  
 Указывает, установлен ли флажок текущей кнопки.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если установлен кнопке текущий; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует различными способами, показывая, что возвращены различные виды кнопок. Например переключатель проверяется, если он содержит точку; будет установлен флажок, если он содержит **X**.  
  
##  <a name="ishighlighted"></a>  CMFCButton::IsHighlighted  
 Указывает, выделяется ли кнопка.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопка выделена; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Кнопка выделяется при наведении указателя мыши на кнопку.  
  
##  <a name="ispressed"></a>  CMFCButton::IsPressed  
 Указывает ли кнопка помещается и выделен.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если при нажатии кнопки; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ispushed"></a>  CMFCButton::IsPushed  
 Указывает, является ли кнопка в нажатом состоянии.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кнопке помещается; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isradiobutton"></a>  CMFCButton::IsRadioButton  
 Указывает, является ли кнопка типа "переключатель".  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если стиль кнопки BS_RADIOBUTTON или BS_AUTORADIOBUTTON; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="iswindowsthemingenabled"></a>  CMFCButton::IsWindowsThemingEnabled  
 Указывает, соответствует ли стиль границы кнопки текущей темы Windows.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если стиль границы кнопки соответствует текущей темы Windows; в противном случае `FALSE`.  
  
##  <a name="m_bdrawfocus"></a>  CMFCButton::m_bDrawFocus  
 Указывает, следует ли прямоугольник фокуса вокруг кнопки.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Примечания  
 Задать `m_bDrawFocus` члена `TRUE` платформа прямоугольник фокуса вокруг текста кнопки и изображения, если кнопка получает фокус.  
  
 `CMFCButton` Конструктор инициализирует этот элемент для `TRUE`.  
  
##  <a name="m_bhighlightchecked"></a>  CMFCButton::m_bHighlightChecked  
 Указывает, следует ли выделять BS_CHECKBOX стиль кнопки при наведении курсора.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Примечания  
 Задать `m_bHighlightChecked` члена `TRUE` для указания, что платформа будет выделяться BS_CHECKBOX стиль кнопки при наведении указателя мыши.  
  
##  <a name="m_brightimage"></a>  CMFCButton::m_bRightImage  
 Указывает, следует ли отображать изображение справа от кнопки.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Примечания  
 Задать `m_bRightImage` члена `TRUE` для указания, что платформа будет отображаться изображение кнопки справа от кнопки текстовой метки.  
  
##  <a name="m_btransparent"></a>  CMFCButton::m_bTransparent  
 Указывает, является ли кнопки прозрачным.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Примечания  
 Задать `m_bTransparent` члена `TRUE` для указания, что платформа будет прозрачной кнопки. `CMFCButton` Конструктор инициализирует этот элемент для `FALSE`.  
  
##  <a name="m_nalignstyle"></a>  CMFCButton::m_nAlignStyle  
 Задает выравнивание текста кнопки.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте один из следующих `CMFCButton::AlignStyle` значений перечисления, чтобы задать выравнивание текста кнопки:  
  
|Значение|Описание:|  
|-----------|-----------------|  
|ALIGN_CENTER|(По умолчанию) Кнопка текст выравнивается по центру кнопки.|  
|ALIGN_LEFT|Кнопка текст выравнивается по левой кнопки.|  
|ALIGN_RIGHT|Кнопка текст выравнивается по правой кнопки.|  
  
 `CMFCButton` Конструктор инициализирует этот элемент для ALIGN_CENTER.  
  
##  <a name="m_nflatstyle"></a>  CMFCButton::m_nFlatStyle  
 Указывает стиль кнопки, например без рамки, плоский, с плоской или объемные эффекты.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице перечислены `CMFCButton::m_nFlatStyle` значения перечисления, которые определяют внешний вид кнопки.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(По умолчанию) Кнопка для высокого уровня, трехмерного сторонами. При нажатии кнопки, кнопка нажатие в глубоких отступов.|  
|BUTTONSTYLE_FLAT|Когда указатель мыши не наведите кнопки, кнопки кажется двухмерный и не имеет вызванное сторон. Когда указатель мыши находится над кнопкой, кнопка появляется низкий, трехмерного сторонами. При нажатии кнопки, кнопка нажатие в неполную отступов.|  
|BUTTONSTYLE_SEMIFLAT|Кнопка для низкий, трехмерного сторонами. При нажатии кнопки, кнопка нажатие в глубоких отступов.|  
|BUTTONSTYLE_NOBORDERS|Кнопка не были поднять сторон и всегда отображается двумерной. Нажатие в отступ при нажатии кнопки не отображается.|  
  
 `CMFCButton` Конструктор инициализирует этот элемент для `BUTTONSTYLE_3D`.  
  
### <a name="example"></a>Пример  
 Ниже приведен пример, как задать значения `m_nFlatStyle` переменной-члена в `CMFCButton` класса. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>  CMFCButton::OnDraw  
 Вызывается платформой для отображения кнопки.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rect*  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
 [in] *uiState*  
 Текущее состояние кнопки. Дополнительные сведения см. в разделе `itemState` членом [DRAWITEMSTRUCT-структура](../../mfc/reference/drawitemstruct-structure.md) раздела.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для отображения кнопки.  
  
##  <a name="ondrawborder"></a>  CMFCButton::OnDrawBorder  
 Вызывается платформой для рисования границы кнопки.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rectClient*  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
 [in] *uiState*  
 Текущее состояние кнопки. Дополнительные сведения см. в разделе `itemState` членом [DRAWITEMSTRUCT-структура](../../mfc/reference/drawitemstruct-structure.md) раздела.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для рисования границы.  
  
##  <a name="ondrawfocusrect"></a>  CMFCButton::OnDrawFocusRect  
 Вызывается платформой для отрисовки прямоугольника фокуса для кнопки.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rectClient*  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для отрисовки прямоугольника фокуса.  
  
##  <a name="ondrawtext"></a>  CMFCButton::OnDrawText  
 Вызывается платформой для отрисовки текста кнопки.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rect*  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
 [in] *strText*  
 Текст для отрисовки.  
  
 [in] *uiDTFlags*  
 Флаги, определяющие способ форматирования текста. Дополнительные сведения см. в разделе *nFormat* параметр [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) метод.  
  
 [in] *uiState*  
 (Зарезервирован.)  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, используемый для отрисовки на кнопке отображается надпись собственный код.  
  
##  <a name="onfillbackground"></a>  CMFCButton::OnFillBackground  
 Вызывается платформой при рисовании фона текста кнопки.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rectClient*  
 Ссылка на прямоугольник, ограничивающий кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы использовать собственный код для рисования фона кнопки.  
  
##  <a name="selectfont"></a>  CMFCButton::SelectFont  
 Возвращает шрифт, который связан с помощью заданного контекста устройств.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Переопределите этот метод, чтобы использовать собственный код для получения шрифта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setautorepeatmode"></a>  CMFCButton::SetAutorepeatMode  
 Задает кнопку в режим автоматического повтора.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nTimeDelay*  
 Неотрицательное число, задающее интервал между сообщений, отправляемых в родительское окно. Интервал измеряется в миллисекундах, и значение по умолчанию равно 500 миллисекунд. Укажите ноль, чтобы отключить режим автоматического повтора сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод приводит к постоянно отправлять сообщения WM_COMMAND родительское окно до освобождения кнопки, кнопки или *nTimeDelay* параметра равным нулю.  
  
##  <a name="setcheckedimage"></a>  CMFCButton::SetCheckedImage  
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
 [in] *hIcon*  
 Дескриптор значок, который содержит точечный рисунок и маски для нового образа.  
  
 [in] *bAutoDestroy*  
 `TRUE` для указания точечного рисунка ресурсы будут уничтожены автоматически; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] *hIconHot*  
 Дескриптор значок, который содержит изображение для выбранного состояния.  
  
 [in] *hBitmap*  
 Дескриптор точечного рисунка, который содержит образ для невыбранных состояния.  
  
 [in] *hBitmapHot*  
 Дескриптор точечного рисунка, который содержит образ для выбранной области.  
  
 [in] *bMap3dColors*  
 Указывает прозрачный цвет фона кнопки; то есть лицевой стороны кнопки. `TRUE` Чтобы использовать значение цвета RGB (192, 192, 192); `FALSE` использовать значение цвета, определяемые `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] *uiBmpResId*  
 Идентификатор ресурса для невыбранных изображения.  
  
 [in] *uiBmpHotResId*  
 Идентификатор ресурса для выбранного образа.  
  
 [in] *hIconDisabled*  
 Дескриптор значок отключенного рисунка.  
  
 [in] *hBitmapDisabled*  
 Дескриптор точечного рисунка, который содержит отключенный образ.  
  
 [in] *uiBmpDsblResID*  
 Идентификатор ресурса точечного рисунка, отключено.  
  
 [in] *bAlphaBlend*  
 `TRUE` для использования только 32-разрядные изображения, использующие альфа-канала; `FALSE`, чтобы не использовать только изображения альфа-канала. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfacecolor"></a>  CMFCButton::SetFaceColor  
 Задает цвет фона для текста кнопки.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *crFace*  
 Значение цвета RGB.  
  
 [in] *bRedraw*  
 `TRUE` Чтобы обновить экран немедленно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить новый цвет заливки фона кнопки (лицевой стороной). Обратите внимание, что фон не будет заполнен при [CMFCButton::m_bTransparent](#m_btransparent) является переменной-члена `TRUE`.  
  
##  <a name="setimage"></a>  CMFCButton::SetImage  
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
 [in] *hIcon*  
 Дескриптор значок, который содержит точечный рисунок и маски для нового образа.  
  
 [in] *bAutoDestroy*  
 `TRUE` для указания точечного рисунка ресурсы будут уничтожены автоматически; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
 [in] *hIconHot*  
 Дескриптор значок, который содержит изображение для выбранного состояния.  
  
 [in] *hBitmap*  
 Дескриптор точечного рисунка, который содержит образ для невыбранных состояния.  
  
 [in] *hBitmapHot*  
 Дескриптор точечного рисунка, который содержит образ для выбранной области.  
  
 [in] *uiBmpResId*  
 Идентификатор ресурса для невыбранных изображения.  
  
 [in] *uiBmpHotResId*  
 Идентификатор ресурса для выбранного образа.  
  
 [in] *bMap3dColors*  
 Указывает прозрачный цвет фона кнопки; то есть лицевой стороны кнопки. `TRUE` Чтобы использовать значение цвета RGB (192, 192, 192); `FALSE` использовать значение цвета, определяемые `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] *hIconDisabled*  
 Дескриптор значок отключенного рисунка.  
  
 [in] *hBitmapDisabled*  
 Дескриптор точечного рисунка, который содержит отключенный образ.  
  
 [in] *uiBmpDsblResID*  
 Идентификатор ресурса точечного рисунка, отключено.  
  
 [in] *bAlphaBlend*  
 `TRUE` для использования только 32-разрядные изображения, использующие альфа-канала; `FALSE`, чтобы не использовать только изображения альфа-канала. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных версий `SetImage` метод `CMFCButton` класса. Пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>  CMFCButton::SetMouseCursor  
 Задает изображение курсора.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *hcursor*  
 Дескриптор курсора.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы связать курсор изображения, например курсор в виде руки, с помощью кнопки. Курсор загружается из ресурсов приложения.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetMouseCursor` метод `CMFCButton` класса. Пример является частью кода в [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>  CMFCButton::SetMouseCursorHand  
 Задает курсор на изображение ладони.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы связать изображение курсора руки с помощью кнопки. Курсор загружается из ресурсов приложения.  
  
##  <a name="setstdimage"></a>  CMFCButton::SetStdImage  
 Использует `CMenuImages` объекта, чтобы задать значок кнопки.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *идентификатор*  
 Один из идентификаторов изображения кнопки, определенные в `CMenuImage::IMAGES_IDS` перечисления. Изображения, например стрелки, ПИН-кодов и переключателей определенные значения изображения.  
  
 [in] *состояния*  
 Один из идентификаторов состояние кнопки изображения, определенные в `CMenuImages::IMAGE_STATE` перечисления. Изображение состояния укажите кнопку цвета, например черный, серый, светло-серый белом и темно-серый. Значение по умолчанию — `CMenuImages::ImageBlack`.  
  
 [in] *idDisabled*  
 Один из идентификаторов изображения кнопки, определенные в `CMenuImage::IMAGES_IDS` перечисления. Изображение показывает, что кнопка отключена. Значение по умолчанию — это первый изображение кнопки ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settextcolor"></a>  CMFCButton::SetTextColor  
 Задает цвет текста кнопки для кнопки, не установлен.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *clrText*  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settexthotcolor"></a>  CMFCButton::SetTextHotColor  
 Задает цвет текста кнопки для кнопки, которая выбрана.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *clrTextHot*  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settooltip"></a>  CMFCButton::SetTooltip  
 Связывает всплывающей подсказки с кнопкой.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszToolTipText*  
 Указатель на текст всплывающей подсказки. Укажите NULL, чтобы отключить подсказки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizetocontent"></a>  CMFCButton::SizeToContent  
 Изменение размера кнопки для хранения его текст кнопки и изображения.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bCalcOnly*  
 `TRUE` вычисления, но не изменять, новый размер кнопки. `FALSE` изменение размера кнопки. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` , содержащий новый размер кнопки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вычисляет новый размер, включающий горизонтальное поле шириной 10 точек и вертикальное поле 5 пикселей.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)   
 [Класс CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)   
 [Класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)
