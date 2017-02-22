---
title: "CMFCButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCButton class"
  - "CMFCButton constructor"
  - "CMFCButton::CreateObject method"
  - "CMFCButton::DrawItem method"
  - "CMFCButton::OnDrawParentBackground method"
  - "CMFCButton::PreTranslateMessage method"
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCButton` добавляет функциональные возможности к классу [CButton](../../mfc/reference/cbutton-class.md), как выравнивание текста кнопки, объединяя текст кнопки и изображение, выбрать курсор и defining подсказка.  
  
## Синтаксис  
  
```  
class CMFCButton : public CButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCButton::CMFCButton`|Конструктор по умолчанию.|  
|`CMFCButton::~CMFCButton`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCButton::CleanUp](../Topic/CMFCButton::CleanUp.md)|Переменные и свободны внутренних возвратов выбранные ресурсы в виде образов, растровые изображения, значки.|  
|`CMFCButton::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCButton::DrawItem`|Вызываемый платформой, когда визуальный аспект определяемой пользователем кнопки изменяется.  \(Переопределяет [CButton::DrawItem](../Topic/CButton::DrawItem.md)\).|  
|[CMFCButton::EnableFullTextTooltip](../Topic/CMFCButton::EnableFullTextTooltip.md)|Указывает, нужно ли отображать полный текст подсказки в большом окне всплывающей подсказки или усеченную версию текста в небольшом окне всплывающей подсказки.|  
|[CMFCButton::EnableMenuFont](../Topic/CMFCButton::EnableMenuFont.md)|Определяет, является ли шрифт текста кнопки такой же, как и шрифт меню приложения.|  
|[CMFCButton::EnableWindowsTheming](../Topic/CMFCButton::EnableWindowsTheming.md)|Определяет, совпадает ли стиль границы кнопки с текущим разделе Windows.|  
|`CMFCButton::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCButton::GetToolTipCtrl](../Topic/CMFCButton::GetToolTipCtrl.md)|Возвращает ссылку на основной элемент управления всплывающей подсказки.|  
|[CMFCButton::IsAutoCheck](../Topic/CMFCButton::IsAutoCheck.md)|Указывает, является ли флажок или переключатель автоматическое.|  
|[CMFCButton::IsAutorepeatCommandMode](../Topic/CMFCButton::IsAutorepeatCommandMode.md)|Указывает, установлена ли кнопка в режим автоповтора.|  
|[CMFCButton::IsCheckBox](../Topic/CMFCButton::IsCheckBox.md)|Указывает, является ли кнопка кнопка "флажок".|  
|[CMFCButton::IsChecked](../Topic/CMFCButton::IsChecked.md)|Показывает, является ли текущая проверена кнопки.|  
|[CMFCButton::IsHighlighted](../Topic/CMFCButton::IsHighlighted.md)|Указывает выделена ли кнопка.|  
|[CMFCButton::IsPressed](../Topic/CMFCButton::IsPressed.md)|Указывает отправлена ли кнопка и выделена.|  
|[CMFCButton::IsPushed](../Topic/CMFCButton::IsPushed.md)|Указывает отправлена ли кнопка.|  
|[CMFCButton::IsRadioButton](../Topic/CMFCButton::IsRadioButton.md)|Указывает, является ли кнопка переключатель.|  
|[CMFCButton::IsWindowsThemingEnabled](../Topic/CMFCButton::IsWindowsThemingEnabled.md)|Указывает, соответствует ли стиль границы кнопки с текущим разделе Windows.|  
|`CMFCButton::OnDrawParentBackground`|Рисует фон родительского элемента кнопки в заданной области.  \(Переопределяет [AFX\_GLOBAL\_DATA::DrawParentBackground](../Topic/AFX_GLOBAL_DATA::DrawParentBackground.md)\).|  
|`CMFCButton::PreTranslateMessage`|Преобразует сообщения окна до их посланы к функциям [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  \(Переопределяет [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)\).|  
|[CMFCButton::SetAutorepeatMode](../Topic/CMFCButton::SetAutorepeatMode.md)|Задает кнопку в режим автоповтора.|  
|[CMFCButton::SetCheckedImage](../Topic/CMFCButton::SetCheckedImage.md)|Задает способ для отмеченных кнопки.|  
|[CMFCButton::SetFaceColor](../Topic/CMFCButton::SetFaceColor.md)|Устанавливает цвет фона текст кнопки.|  
|[CMFCButton::SetImage](../Topic/CMFCButton::SetImage.md)|Задает способ для кнопки.|  
|[CMFCButton::SetMouseCursor](../Topic/CMFCButton::SetMouseCursor.md)|Задает способ курсора.|  
|[CMFCButton::SetMouseCursorHand](../Topic/CMFCButton::SetMouseCursorHand.md)|Устанавливает курсор на образу руки.|  
|[CMFCButton::SetStdImage](../Topic/CMFCButton::SetStdImage.md)|Использует объект `CMenuImages` чтобы задать изображение кнопки.|  
|[CMFCButton::SetTextColor](../Topic/CMFCButton::SetTextColor.md)|Задает цвет текста кнопки для кнопки, не выделена.|  
|[CMFCButton::SetTextHotColor](../Topic/CMFCButton::SetTextHotColor.md)|Задает цвет текста кнопки для кнопки, выделена.|  
|[CMFCButton::SetTooltip](../Topic/CMFCButton::SetTooltip.md)|Связывает подсказка с кнопкой.|  
|[CMFCButton::SizeToContent](../Topic/CMFCButton::SizeToContent.md)|Изменяет размер кнопку, чтобы содержать его текст и изображение кнопки.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCButton::OnDraw](../Topic/CMFCButton::OnDraw.md)|Вызываемый платформой для рисования кнопки.|  
|[CMFCButton::OnDrawBorder](../Topic/CMFCButton::OnDrawBorder.md)|Вызываемый платформой для рисования границы кнопки.|  
|[CMFCButton::OnDrawFocusRect](../Topic/CMFCButton::OnDrawFocusRect.md)|Вызываемый платформой, чтобы нарисовать прямоугольник фокуса для кнопки.|  
|[CMFCButton::OnDrawText](../Topic/CMFCButton::OnDrawText.md)|Вызываемый платформой для рисования текста кнопки.|  
|[CMFCButton::OnFillBackground](../Topic/CMFCButton::OnFillBackground.md)|Вызываемый платформой для рисования фона текст кнопки.|  
|[CMFCButton::SelectFont](../Topic/CMFCButton::SelectFont.md)|Получает шрифт, который связан с указанным контекстом устройства.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCButton::m\_bDrawFocus](../Topic/CMFCButton::m_bDrawFocus.md)|Указывает, следует ли нарисовать прямоугольник фокуса вокруг кнопки.|  
|[CMFCButton::m\_bHighlightChecked](../Topic/CMFCButton::m_bHighlightChecked.md)|Указывает, является ли выбрать BS\_CHECKBOX\-style застегните диапазона, когда курсор над ним.|  
|[CMFCButton::m\_bRightImage](../Topic/CMFCButton::m_bRightImage.md)|Указывает, отображать ли образ справа от кнопки.|  
|[CMFCButton::m\_bTransparent](../Topic/CMFCButton::m_bTransparent.md)|Указывает, является ли кнопка прозрачна.|  
|[CMFCButton::m\_nAlignStyle](../Topic/CMFCButton::m_nAlignStyle.md)|Определяет выравнивание текста кнопки.|  
|[CMFCButton::m\_nFlatStyle](../Topic/CMFCButton::m_nFlatStyle.md)|Задает стиль кнопки, как borderless, горизонтальных стрелок, semi\- или объемные эффекты.|  
  
## Заметки  
 Другие типы кнопок производными от класса `CMFCButton`, как класс [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md), который поддерживает гиперссылки и класс `CMFCColorButton`, который поддерживает диалоговое окно палитра цветов.  
  
 Стиль объекта `CMFCButton` может быть *выпуклая граница*, *плосок*, *semi\- плосок* или *граница*.  Текст кнопки можно выравнивать слева, перекрывает или центре кнопки.  Во время выполнения можно контролировать вставке СМС отображается ли кнопки, изображение или текст и изображение.  Можно также указать, что конкретный способ курсора был отображается в случае, если курсор изменяется на кнопку.  
  
 Создайте элемент управления "Кнопка" или непосредственно в коде или с помощью средства **Мастер классов MFC** и шаблона диалогового окна.  Если создается элемент управления "Кнопка", то добавьте переменную `CMFCButton` в приложение, затем вызовите конструктор и методы `Create``CMFCButton` объект.  При использовании **Мастер классов MFC**, добавьте переменную `CButton` в приложение, а затем измените тип переменной из `CButton` к `CMFCButton`.  
  
 Для обработки сообщений уведомлений приложение диалогового окна добавьте запись сопоставления сообщений и обработчик событий для каждого уведомления.  Уведомления, отправленные объектом `CMFCButton` эти же, что и `CButton`, переданные объектом.  
  
## Пример  
 В следующем примере показано, как настроить свойства кнопок с использованием различных методов в классе `CMFCButton`.  Пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_4.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## Требования  
 **заголовок:** afxbutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCLinkCtrl Class](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)   
 [Класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)