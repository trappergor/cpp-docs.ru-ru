---
title: "CMFCBaseVisualManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseVisualManager"
  - "CMFCBaseVisualManager.~CMFCBaseVisualManager"
  - "~CMFCBaseVisualManager"
  - "CMFCBaseVisualManager::~CMFCBaseVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseVisualManager destructor"
  - "CMFCBaseVisualManager class"
  - "CMFCBaseVisualManager class, деструктор"
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCBaseVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Уровень между производными диспетчерами визуального представления и разделы api\-интерфейса Windows.  
  
 `CMFCBaseVisualManager` загружает UxTheme.dll, если он доступен и управляет доступом к методам API разделах Windows.  
  
 Этот класс предназначен только для внутреннего использования.  
  
## Синтаксис  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](../Topic/CMFCBaseVisualManager::CMFCBaseVisualManager.md)|Создания и инициализации объект `CMFCBaseVisualManager`.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Деструктор.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::DrawCheckBox](../Topic/CMFCBaseVisualManager::DrawCheckBox.md)|Рисует элемент управления "флажок", используя текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawComboBorder](../Topic/CMFCBaseVisualManager::DrawComboBorder.md)|Рисует границу поля со списком с помощью текущую тему Windows.|  
|[CMFCBaseVisualManager::DrawComboDropButton](../Topic/CMFCBaseVisualManager::DrawComboDropButton.md)|Рисует кнопку раскрывающегося списка в поле со списком, используя текущую тему Windows.|  
|[CMFCBaseVisualManager::DrawPushButton](../Topic/CMFCBaseVisualManager::DrawPushButton.md)|Рисует кнопку, используя текущую тему Windows.|  
|[CMFCBaseVisualManager::DrawRadioButton](../Topic/CMFCBaseVisualManager::DrawRadioButton.md)|Рисует элемент управления переключателя с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](../Topic/CMFCBaseVisualManager::DrawStatusBarProgress.md)|Рисует индикатор выполнения в элементе управления "Строка состояния" \([CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)\) с помощью текущую тему Windows.|  
|[CMFCBaseVisualManager::FillReBarPane](../Topic/CMFCBaseVisualManager::FillReBarPane.md)|Заполняет фон элемента управления "Главная панель" с помощью текущей темы Windows.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](../Topic/CMFCBaseVisualManager::GetStandardWindowsTheme.md)|Возвращает текущую тему Windows.|  
  
### Защищенные методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCBaseVisualManager::CleanUpThemes](../Topic/CMFCBaseVisualManager::CleanUpThemes.md)|Вызывает `CloseThemeData` для всех маркеров, полученных в `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](../Topic/CMFCBaseVisualManager::UpdateSystemColors.md)|Вызывает `OpenThemeData` чтобы получить маркеры для рисования различные элементы управления: окна, панели инструментов, кнопки и т д|  
  
## Заметки  
 Нет необходимости создавать объекты экземпляра этого класса напрямую.  
  
 Поскольку базовый класс для всех диспетчеров визуального представления можно просто вызвать [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md), получить указатель на текущий диспетчер визуального представления и получить доступ к методам для `CMFCBaseVisualManager`, использующие этот указатель.  Однако если необходимо отображать элемент управления с использованием текущей темы Windows, то лучше использовать интерфейс `CMFCVisualManagerWindows`.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## Требования  
 **заголовок:** afxvisualmanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)