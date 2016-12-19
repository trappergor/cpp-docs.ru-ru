---
title: "CMFCFontComboBox Class | Microsoft Docs"
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
  - "CMFCFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontComboBox class"
  - "CMFCFontComboBox::CompareItem method"
  - "CMFCFontComboBox::DrawItem method"
  - "CMFCFontComboBox::MeasureItem method"
  - "CMFCFontComboBox::PreTranslateMessage method"
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCFontComboBox` создает элемент управления поля со списком, содержащий список шрифтов.  
  
## Синтаксис  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCFontComboBox::CMFCFontComboBox](../Topic/CMFCFontComboBox::CMFCFontComboBox.md)|Создает объект `CMFCFontComboBox`.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCFontComboBox::CompareItem`|Вызываемый платформой, чтобы указать относительное положение нового элемента в сортированном списке текущего элемента управления " поле со списком шрифт.  \(Переопределяет [CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md)\).|  
|`CMFCFontComboBox::DrawItem`|Вызываемый платформой для рисования указанный элемент в текущем элементе управления поля со списком шрифт.  \(Переопределяет [CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md)\).|  
|[CMFCFontComboBox::GetSelFont](../Topic/CMFCFontComboBox::GetSelFont.md)|Извлекает сведения о текущем выбранном шрифте.|  
|`CMFCFontComboBox::MeasureItem`|Вызываемый платформой для оповещения Windows измерений списка в текущем элементе управления поля со списком шрифт.  \(Переопределяет [CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md)\).|  
|`CMFCFontComboBox::PreTranslateMessage`|Преобразует сообщения окна до их посланы к функциям [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  \(Переопределяет [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)\).|  
|[CMFCFontComboBox::SelectFont](../Topic/CMFCFontComboBox::SelectFont.md)|Выбирает шрифт, соответствующий заданным критериям из поля со списком шрифт.|  
|[CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md)|Инициализирует список элементов в поле со списком шрифт.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCFontComboBox::m\_bDrawUsingFont](../Topic/CMFCFontComboBox::m_bDrawUsingFont.md)|Указывает к рамкам, шрифт, используемый для рисования элемента обозначает в текущем поле со списком шрифт.|  
  
## Заметки  
 Чтобы использовать объект `CMFCFontComboBox` в диалоговом окне добавить переменную `CMFCFontComboBox` к классу диалогового окна.  Затем в методе `OnInitDialog` класса диалогового окна, вызовите метод [CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md) для инициализации список элементов в элементе управления поля со списком.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## Требования  
 **заголовок:** afxfontcombobox.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)