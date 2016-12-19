---
title: "CMFCRibbonEdit Class | Microsoft Docs"
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
  - "CMFCRibbonEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonEdit class"
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует элемент управления "Поле ввода", найти на панели ленты.  
  
## Синтаксис  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|Создает объект `CMFCRibbonEdit`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonEdit::CanBeStretched](../Topic/CMFCRibbonEdit::CanBeStretched.md)|Указывает, является ли высота элемента управления `CMFCRibbonEdit` может увеличиваться по вертикали для высоты строки ленты.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|Создает объект `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::CopyFrom](../Topic/CMFCRibbonEdit::CopyFrom.md)|Копирует состояние указанного объекта `CMFCRibbonEdit` к текущему объекту `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::CreateEdit](../Topic/CMFCRibbonEdit::CreateEdit.md)|Создает новое текстовое поле для объекта `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::DestroyCtrl](../Topic/CMFCRibbonEdit::DestroyCtrl.md)|Уничтожает объект `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::DropDownList](../Topic/CMFCRibbonEdit::DropDownList.md)|Удаляет вниз по списку.|  
|[CMFCRibbonEdit::EnableSpinButtons](../Topic/CMFCRibbonEdit::EnableSpinButtons.md)|Включает и задает диапазон кнопки прокруток для текстового поля.|  
|[CMFCRibbonEdit::GetCompactSize](../Topic/CMFCRibbonEdit::GetCompactSize.md)|Извлекает компактный размер объекта `CFMCRibbonEdit`.|  
|[CMFCRibbonEdit::GetEditText](../Topic/CMFCRibbonEdit::GetEditText.md)|Извлекает текст в текстовом поле.|  
|[CMFCRibbonEdit::GetIntermediateSize](../Topic/CMFCRibbonEdit::GetIntermediateSize.md)|Возвращает средний размер объекта `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::GetTextAlign](../Topic/CMFCRibbonEdit::GetTextAlign.md)|Получает выравнивание текста в текстовом поле.|  
|[CMFCRibbonEdit::GetWidth](../Topic/CMFCRibbonEdit::GetWidth.md)|Получает толщину \(в точках\) элемента управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::HasCompactMode](../Topic/CMFCRibbonEdit::HasCompactMode.md)|Указывает, является ли размер отображения для управления `CMFCRibbonEdit` может быть компактн.|  
|[CMFCRibbonEdit::HasFocus](../Topic/CMFCRibbonEdit::HasFocus.md)|Указывает, имеет ли элемент управления `CMFCRIbbonEdit` фокус.|  
|[CMFCRibbonEdit::HasLargeMode](../Topic/CMFCRibbonEdit::HasLargeMode.md)|Указывает, является ли размер отображения для управления `CMFCRibbonEdit` может быть большим.|  
|[CMFCRibbonEdit::HasSpinButtons](../Topic/CMFCRibbonEdit::HasSpinButtons.md)|Указывает, имеет ли текстовое поле кнопку "счетчик".|  
|[CMFCRibbonEdit::IsHighlighted](../Topic/CMFCRibbonEdit::IsHighlighted.md)|Указывает выделен, является ли элемент управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::OnAfterChangeRect](../Topic/CMFCRibbonEdit::OnAfterChangeRect.md)|Вызываемый платформой, когда измерения прямоугольника отображения для элемента управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::OnDraw](../Topic/CMFCRibbonEdit::OnDraw.md)|Вызываемый платформой для отрисовки элемента управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](../Topic/CMFCRibbonEdit::OnDrawLabelAndImage.md)|Вызываемый платформой для рисования метку и изображение для элемента управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::OnDrawOnList](../Topic/CMFCRibbonEdit::OnDrawOnList.md)|Вызываемый платформой для отрисовки элемента управления `CMFCRibbonEdit` в списке команды.|  
|[CMFCRibbonEdit::OnEnable](../Topic/CMFCRibbonEdit::OnEnable.md)|Вызываемый платформой, чтобы включить или отключить элемент управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::OnHighlight](../Topic/CMFCRibbonEdit::OnHighlight.md)|Вызываемый платформой, когда указатель покидает границы элемента управления или вводит `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::OnKey](../Topic/CMFCRibbonEdit::OnKey.md)|Вызываемый платформой, когда пользователь нажимает keytip и управление `CMFCRibbonEdit` имеет фокус.|  
|[CMFCRibbonEdit::OnLButtonDown](../Topic/CMFCRibbonEdit::OnLButtonDown.md)|Вызываемый платформой, чтобы обновить элемент управления `CMFCRibbonEdit`, когда пользователь отожмет нажатие левой кнопки мыши на элементе управления.|  
|[CMFCRibbonEdit::OnLButtonUp](../Topic/CMFCRibbonEdit::OnLButtonUp.md)|Вызываемый платформой, когда пользователь освобождает нажатие левой кнопки мыши.|  
|[CMFCRibbonEdit::OnRTLChanged](../Topic/CMFCRibbonEdit::OnRTLChanged.md)|Вызываемый платформой, чтобы обновить элемент управления `CMFCRibbonEdit`, если структура изменяет направление.|  
|[CMFCRibbonEdit::OnShow](../Topic/CMFCRibbonEdit::OnShow.md)|Вызываемый платформой, чтобы отображать или скрывать элемент управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::Redraw](../Topic/CMFCRibbonEdit::Redraw.md)|Обновляет отображение управления `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::SetACCData](../Topic/CMFCRibbonEdit::SetACCData.md)|Задает сведения о специальных возможностей для объекта `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::SetEditText](../Topic/CMFCRibbonEdit::SetEditText.md)|Устанавливает текст в текстовом поле.|  
|[CMFCRibbonEdit::SetTextAlign](../Topic/CMFCRibbonEdit::SetTextAlign.md)|Задает выравнивание текста в текстовом поле.|  
|[CMFCRibbonEdit::SetWidth](../Topic/CMFCRibbonEdit::SetWidth.md)|Задает ширину текстового поля для управления `CMFCRibbonEdit`.|  
  
## Заметки  
  
## Пример  
 В следующем примере показано, как создать объект `CMFCRibbonEdit` показать, закрутка застегивает рядом с элементом управления "Поле ввода" и задайте текст элемента управления "Поле ввода".  Этот фрагмент кода является частью [Пример demo MS office 2007](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/CPP/cmfcribbonedit-class_1.cpp)]  
  
## Требования  
 **заголовок:** afxRibbonEdit.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)