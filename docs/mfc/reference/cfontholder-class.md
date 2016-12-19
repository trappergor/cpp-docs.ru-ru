---
title: "CFontHolder Class | Microsoft Docs"
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
  - "CFontHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontHolder class"
  - "custom fonts"
  - "шрифты, элементы управления ActiveX"
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFontHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует свойство шрифта и стандартные функциональные возможности объекта шрифта Windows и интерфейса `IFont`.  
  
## Синтаксис  
  
```  
class CFontHolder  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFontHolder::CFontHolder](../Topic/CFontHolder::CFontHolder.md)|Создает объект `CFontHolder`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFontHolder::GetDisplayString](../Topic/CFontHolder::GetDisplayString.md)|Извлекает строку, отображаемой в обозревателе свойств контейнера.|  
|[CFontHolder::GetFontDispatch](../Topic/CFontHolder::GetFontDispatch.md)|Возвращает интерфейс `IDispatch` шрифта.|  
|[CFontHolder::GetFontHandle](../Topic/CFontHolder::GetFontHandle.md)|Возвращает дескриптор к шрифту Windows.|  
|[CFontHolder::InitializeFont](../Topic/CFontHolder::InitializeFont.md)|Инициализирует объект `CFontHolder`.|  
|[CFontHolder::QueryTextMetrics](../Topic/CFontHolder::QueryTextMetrics.md)|Извлекает сведения для связанного шрифта.|  
|[CFontHolder::ReleaseFont](../Topic/CFontHolder::ReleaseFont.md)|Отключает объект `CFontHolder` из интерфейсов `IFont` и `IFontNotification`.|  
|[CFontHolder::Select](../Topic/CFontHolder::Select.md)|Выберите ресурс шрифта в контекст устройства.|  
|[CFontHolder::SetFont](../Topic/CFontHolder::SetFont.md)|Объект `CFontHolder` подключается к интерфейсу `IFont`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFontHolder::m\_pFont](../Topic/CFontHolder::m_pFont.md)|Указатель на интерфейс `IFont` объекта `CFontHolder`.|  
  
## Заметки  
 `CFontHolder` не имеет базовый класс.  
  
 Этот класс используется для предоставления свойств пользовательского шрифта для элемента управления.  Дополнительные сведения о создании этих свойств см. в статье [Элементы управления ActiveX. Использование шрифтов](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## Иерархия наследования  
 `CFontHolder`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPropExchange Class](../Topic/CPropExchange%20Class.md)