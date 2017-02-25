---
title: "Класс CLinearTransition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CLinearTransition"
  - "afxanimationcontroller/CLinearTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransition - класс"
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс CLinearTransition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует линейный переход.  
  
## Синтаксис  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinearTransition::CLinearTransition](../Topic/CLinearTransition::CLinearTransition.md)|Создает объект линейного перехода и инициализирует его длительностью и конечным значением.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinearTransition::Create](../Topic/CLinearTransition::Create.md)|Вызывается библиотекой переходов для создания инкапсулированного COM\-объекта перехода.  \(Переопределяет [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinearTransition::m\_dblFinalValue](../Topic/CLinearTransition::m_dblFinalValue.md)|Значение переменной анимации в конце перехода.|  
|[CLinearTransition::m\_duration](../Topic/CLinearTransition::m_duration.md)|Длительность перехода.|  
  
## Заметки  
 Во время линейного перехода значение переменной анимации изменяется линейно от начального значения до заданного конечного значения.  Поскольку все переходы удаляются автоматически, рекомендуется размещать их в стеке с помощью оператора new.  Инкапсулированный COM\-объект IUIAnimationTransition создается методом CAnimationController::AnimateGrou; до этого он имеет значение NULL.  Изменение переменных\-членов после создания этого COM\-объекта ни на что не влияет.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)