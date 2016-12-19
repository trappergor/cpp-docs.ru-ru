---
title: "CMFCColorButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorButton class"
  - "CMFCColorButton::m_bAltColorDlg data member"
  - "CMFCColorButton::m_bAutoSetFocus data member"
  - "CMFCColorButton::m_Color data member"
  - "CMFCColorButton::m_ColorAutomatic data member"
  - "CMFCColorButton::m_lstDocColors data member"
  - "CMFCColorButton::m_nColumns data member"
  - "CMFCColorButton::m_pPalette data member"
  - "CMFCColorButton::m_pPopup data member"
  - "CMFCColorButton::m_strAutoColorText data member"
  - "CMFCColorButton::m_strDocColorsText data member"
  - "CMFCColorButton::m_strOtherText data member"
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorButton` и классы [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md) используются совместно, чтобы реализовать управление палитры.  
  
## Синтаксис  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorButton::CMFCColorButton](../Topic/CMFCColorButton::CMFCColorButton.md)|Создает новый объект `CMFCColorButton`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorButton::EnableAutomaticButton](../Topic/CMFCColorButton::EnableAutomaticButton.md)|Включает и блокирует "," автоматическая кнопку, которая располагается на обычный кнопками цвета.  \(Кнопка стандартной системы автоматическая на которую указывает **Автоматически**\).|  
|[CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)|Включает и блокирует "другой" кнопку, которая располагается под обычный кнопками цвета.  \(Стандартная система "другой" указывает **More Colors…**\).|  
|[CMFCColorButton::GetAutomaticColor](../Topic/CMFCColorButton::GetAutomaticColor.md)|Извлекает текущий автоцвет.|  
|[CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md)|Получает цвет кнопки.|  
|[CMFCColorButton::SetColor](../Topic/CMFCColorButton::SetColor.md)|Устанавливает цвет кнопки.|  
|[CMFCColorButton::SetColorName](../Topic/CMFCColorButton::SetColorName.md)|Задает имя цвета.|  
|[CMFCColorButton::SetColumnsNumber](../Topic/CMFCColorButton::SetColumnsNumber.md)|Задает число столбцов в диалоговом окне палитра цветов.|  
|[CMFCColorButton::SetDocumentColors](../Topic/CMFCColorButton::SetDocumentColors.md)|Определяет список цветов документ\- определенной, отображаемых в диалоговом окне палитра цветов.|  
|[CMFCColorButton::SetPalette](../Topic/CMFCColorButton::SetPalette.md)|Задает палитру стандартных цветов отображения.|  
|[CMFCColorButton::SizeToContent](../Topic/CMFCColorButton::SizeToContent.md)|Изменяет размер элемента управления "Кнопка", в зависимости от его текст и размер образа.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorButton::IsDrawXPTheme](../Topic/CMFCColorButton::IsDrawXPTheme.md)|Указывает, отображается ли текущая кнопку цвета в визуальном стиле Windows XP.|  
|[CMFCColorButton::OnDraw](../Topic/CMFCColorButton::OnDraw.md)|Вызываемый платформой для отображения образа кнопки.|  
|[CMFCColorButton::OnDrawBorder](../Topic/CMFCColorButton::OnDrawBorder.md)|Вызываемый платформой, чтобы отобразить границы кнопки.|  
|[CMFCColorButton::OnDrawFocusRect](../Topic/CMFCColorButton::OnDrawFocusRect.md)|Вызываемый платформой для отображения прямоугольника фокуса когда кнопка будет иметь фокус.|  
|[CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)|Вызываемый платформой, когда диалоговое окно "Палитра цветов" будет отображаться.|  
|[CMFCColorButton::RebuildPalette](../Topic/CMFCColorButton::RebuildPalette.md)|Инициализирует элемент данных, защищенный `m_pPalette` в палитре или заданной по умолчанию палитре системы.|  
|[CMFCColorButton::UpdateColor](../Topic/CMFCColorButton::UpdateColor.md)|Вызываемый платформой, когда пользователь выбирает цвета из палитры диалогового окна палитра цветов.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|`m_bAltColorDlg`|Логическое значение.  Если `TRUE`, платформа отображает диалоговое окно цвета [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md), если *еще одну* кнопку нажата или если `FALSE`, то диалоговое окно цвет системы.  Значение по умолчанию — `TRUE`.  Дополнительные сведения см. в разделе [CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md).|  
|`m_bAutoSetFocus`|Логическое значение.  Если `TRUE` платформа устанавливает фокус в меню, когда меню отображается цвета или если `FALSE`, не меняет фокус.  Значение по умолчанию — `TRUE`.|  
|[CMFCColorButton::m\_bEnabledInCustomizeMode](../Topic/CMFCColorButton::m_bEnabledInCustomizeMode.md)|Указывает, включен ли режим настройки цвета для кнопки.|  
|`m_Color`|Значение [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449).  Содержит текущий выбранный цвет.|  
|`m_ColorAutomatic`|Значение [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449).  Содержит текущий выбранный цвет по умолчанию.|  
|`m_Colors`|[CArray](../../mfc/reference/carray-class.md) значений [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449).  Содержит в данный момент доступные цвета.|  
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) значений [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449).  Содержит цвета текущего документа.|  
|`m_nColumns`|Параметр типа Integer \(целое число\).  Содержит количество столбцов для отображения в сетке цветов в меню выбора цвета.|  
|`m_pPalette`|Указатель на [CPalette](../../mfc/reference/cpalette-class.md).  Содержит цвета, доступные в текущем меню выбора цвета.|  
|`m_pPopup`|Указатель на объект [CMFCColorPopupMenu Class](../Topic/CMFCColorPopupMenu%20Class.md).  Меню выбора цвета, который отображается при нажатии кнопки цвета.|  
|`m_strAutoColorText`|Строка.  Метка "автоматической" кнопки в меню выбора цвета.|  
|`m_strDocColorsText`|Строка.  Метка кнопки в меню выбора цвета, указывающее цвет рисования.|  
|`m_strOtherText`|Строка.  Метка "другой" в меню выбора цвета.|  
  
## Заметки  
 По умолчанию класс `CMFCColorButton` действовать как кнопка, которая открывает диалоговое окно палитра цветов.  Диалоговое окно "Палитра цветов" содержит массив небольших кнопок и "другой" кнопка, которая показывает выбор настраиваемых цветов.  \(Стандартная система "другой" указывает **More Colors…**\). Когда пользователь выделяет новый цвет, объект `CMFCColorButton` отражает изменения и отображает выбранный цвет.  
  
 Создайте элемент управления "Кнопка" цвета или непосредственно в коде или с помощью средства **ClassWizard** и шаблона диалогового окна.  Если создается элемент управления "Кнопка" цвета напрямую, то добавьте переменную `CMFCColorButton` в приложение, затем вызовите конструктор и методы `Create``CMFCColorButton` объект.  При использовании **ClassWizard**, добавьте переменную `CButton` в приложение, а затем измените тип переменной из `CButton` к `CMFCColorButton`.  
  
 Диалоговое окно "Палитра цветов" \([CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)\) показано методом [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md), когда платформа вызывает функцию обработчика событий `OnLButtonDown`.  [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) метод можно переопределить, чтобы поддерживать выделение пользовательского цвета.  
  
 Объект `CMFCColorButton` уведомляет его родительским элементом, что цвет изменяет его путем отправки уведомления `WM_COMMAND | BN_CLICKED`.  Родительский элемент использует метод [CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md) чтобы получить текущий цвет.  
  
## Пример  
 В следующем примере показано, как настроить кнопку цвета с помощью различных методов в классе `CMFCColorButton`.  Методы устанавливают цвет кнопки цвета и его числа столбцов и включают автоматических и другие кнопки.  Данный пример является частью [Пример demo строки состояния](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_2.cpp)]  
  
## Требования  
 **заголовок:** afxcolorbutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)