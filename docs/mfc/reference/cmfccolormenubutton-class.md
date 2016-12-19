---
title: "CMFCColorMenuButton Class | Microsoft Docs"
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
  - "CMFCColorMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorMenuButton class"
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCColorMenuButton` поддерживает команду меню или кнопки панели инструментов, которая запускает диалоговое окно палитра цветов.  
  
## Синтаксис  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](../Topic/CMFCColorMenuButton::CMFCColorMenuButton.md)|Создает объект `CMFCColorMenuButton`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](../Topic/CMFCColorMenuButton::EnableAutomaticButton.md)|Включает и блокирует "," автоматическая кнопку, которая располагается на обычный кнопками цвета.  \(Кнопка стандартной системы автоматическая на которую указывает **Автоматически**\).|  
|[CMFCColorMenuButton::EnableDocumentColors](../Topic/CMFCColorMenuButton::EnableDocumentColors.md)|Включает отображение цвета вместо цветов документ\- определенной системы.|  
|[CMFCColorMenuButton::EnableOtherButton](../Topic/CMFCColorMenuButton::EnableOtherButton.md)|Включает и блокирует "другой" кнопку, которая располагается под обычный кнопками цвета.  \(Стандартная система "другой" указывает **More Colors…**\).|  
|[CMFCColorMenuButton::EnableTearOff](../Topic/CMFCColorMenuButton::EnableTearOff.md)|Включает возможность сорвать панель цвета.|  
|[CMFCColorMenuButton::GetAutomaticColor](../Topic/CMFCColorMenuButton::GetAutomaticColor.md)|Извлекает текущий автоцвет.|  
|[CMFCColorMenuButton::GetColor](../Topic/CMFCColorMenuButton::GetColor.md)|Извлекает текущий цвет кнопки.|  
|[CMFCColorMenuButton::GetColorByCmdID](../Topic/CMFCColorMenuButton::GetColorByCmdID.md)|Получает цвет, соответствующий указанному идентификатору команды|  
|[CMFCColorMenuButton::OnChangeParentWnd](../Topic/CMFCColorMenuButton::OnChangeParentWnd.md)|Вызываемый платформой, если родительское окно изменяется.|  
|[CMFCColorMenuButton::OpenColorDialog](../Topic/CMFCColorMenuButton::OpenColorDialog.md)|Открывает диалоговое окно выбора цвета.|  
|[CMFCColorMenuButton::SetColor](../Topic/CMFCColorMenuButton::SetColor.md)|Устанавливает цвет текущей кнопки цвета.|  
|[CMFCColorMenuButton::SetColorByCmdID](../Topic/CMFCColorMenuButton::SetColorByCmdID.md)|Устанавливает цвет палитры указанной кнопки.|  
|[CMFCColorMenuButton::SetColorName](../Topic/CMFCColorMenuButton::SetColorName.md)|Устанавливает новое имя для указанного цвета.|  
|[CMFCColorMenuButton::SetColumnsNumber](../Topic/CMFCColorMenuButton::SetColumnsNumber.md)|Устанавливает количество столбцов, отображаемых объектом `CMFCColorBar`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorMenuButton::CopyFrom](../Topic/CMFCColorMenuButton::CopyFrom.md)|Копирует вторая кнопка панели инструментов с текущим кнопке.|  
|[CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md)|Создает диалоговое окно палитра цветов.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](../Topic/CMFCColorMenuButton::IsEmptyMenuAllowed.md)|Указывает, поддерживаются ли пустые меню.|  
|[CMFCColorMenuButton::OnDraw](../Topic/CMFCColorMenuButton::OnDraw.md)|Вызываемый платформой для отображения образа на кнопке.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](../Topic/CMFCColorMenuButton::OnDrawOnCustomizeList.md)|Вызываемый платформой, прежде чем объект `CMFCColorMenuButton` будет отображаться в списке диалогового окна настройки панели инструментов.|  
  
## Заметки  
 Чтобы заменить исходный команду меню или кнопки панели инструментов с объектом `CMFCColorMenuButton` создайте объект `CMFCColorMenuButton` задайте все соответствующие стили [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md), и затем вызовите метод `ReplaceButton` класса [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  Если вы настраиваете панель инструментов, вызовите метод [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md).  
  
 Диалоговое окно "Палитра цветов" создано во время обработки метод обработчика событий [CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md).  Обработчик событий уведомляет родительский кадр с сообщением `WM_COMMAND`.  Объект `CMFCColorMenuButton` отправляет идентификатор элемента управления, присвоено к исходной команде меню или кнопке панели инструментов.  
  
## Пример  
 В следующем примере показано, как создать и настроить кнопку палитры с помощью различных методов в классе `CMFCColorMenuButton`.  В этом примере объект `CPalette` сначала создать, а затем используется для создания объекта класса `CMFCColorMenuButton`.  Объект `CMFCColorMenuButton` затем настроить, позволяя его автоматических и другие кнопки и установление его цвет и число столбцов.  Данный пример кода является частью [Пример запуска площадки слова](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## Требования  
 **заголовок:** afxcolormenubutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)