---
title: "Класс CAnimationGroup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationGroup"
  - "CAnimationGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationGroup - класс"
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс CAnimationGroup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует группу анимации, объединяющую раскадровку анимации, объекты анимации и переходы, определяющие анимацию.  
  
## Синтаксис  
  
```  
class CAnimationGroup;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationGroup::CAnimationGroup](../Topic/CAnimationGroup::CAnimationGroup.md)|Создает группу анимации.|  
|[CAnimationGroup::~CAnimationGroup](../Topic/CAnimationGroup::~CAnimationGroup.md)|Деструктор.  Вызывается при уничтожении группы анимации.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationGroup::Animate](../Topic/CAnimationGroup::Animate.md)|Анимирует группу.|  
|[CAnimationGroup::ApplyTransitions](../Topic/CAnimationGroup::ApplyTransitions.md)|Применяет переходы к объектам анимации.|  
|[CAnimationGroup::FindAnimationObject](../Topic/CAnimationGroup::FindAnimationObject.md)|Находит объект анимации, содержащий заданную переменную анимации.|  
|[CAnimationGroup::GetGroupID](../Topic/CAnimationGroup::GetGroupID.md)|Возвращает ИД группы.|  
|[CAnimationGroup::RemoveKeyframes](../Topic/CAnimationGroup::RemoveKeyframes.md)|Удаляет и \(необязательно\) уничтожает все опорные кадры, принадлежащие к группе анимации.|  
|[CAnimationGroup::RemoveTransitions](../Topic/CAnimationGroup::RemoveTransitions.md)|Удаляет переходы из объектов анимации, принадлежащих к группе анимации.|  
|[CAnimationGroup::Schedule](../Topic/CAnimationGroup::Schedule.md)|Планирует анимацию на заданное время.|  
|[CAnimationGroup::SetAutodestroyTransitions](../Topic/CAnimationGroup::SetAutodestroyTransitions.md)|Дает всем принадлежащим к группе объектам анимации указание автоматически уничтожать переходы.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationGroup::AddKeyframes](../Topic/CAnimationGroup::AddKeyframes.md)|Вспомогательный метод, добавляющий опорные кадры в раскадровку.|  
|[CAnimationGroup::AddTransitions](../Topic/CAnimationGroup::AddTransitions.md)|Вспомогательный метод, добавляющий переходы в раскадровку.|  
|[CAnimationGroup::CreateTransitions](../Topic/CAnimationGroup::CreateTransitions.md)|Вспомогательный метод, создающий COM\-объекты переходов.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationGroup::m\_bAutoclearTransitions](../Topic/CAnimationGroup::m_bAutoclearTransitions.md)|Указывает, как удалять переходы из объектов анимации, принадлежащих к группе.  Если этот член имеет значение TRUE, после того, как анимация запланирована, переходы автоматически удаляются.  В противном случае удалять переходы необходимо вручную.|  
|[CAnimationGroup::m\_bAutodestroyAnimationObjects](../Topic/CAnimationGroup::m_bAutodestroyAnimationObjects.md)|Указывает, как уничтожать объекты анимации.  Если этот параметр имеет значение TRUE, объекты анимации автоматически уничтожаются при уничтожении группы.  В противном случае уничтожать объекты анимации необходимо вручную.  Значение по умолчанию — FALSE.  Устанавливайте это значение равным TRUE, только если все принадлежащие к группе объекты анимации размещаются автоматически с помощью оператора new.|  
|[CAnimationGroup::m\_bAutodestroyKeyframes](../Topic/CAnimationGroup::m_bAutodestroyKeyframes.md)|Указывает, как уничтожать опорные кадры.  Если это значение — TRUE, все опорные кадры удаляются и уничтожаются; в противном случае они только удаляются из списка.  Значение по умолчанию \- TRUE.|  
|[CAnimationGroup::m\_lstAnimationObjects](../Topic/CAnimationGroup::m_lstAnimationObjects.md)|Содержит список объектов анимации.|  
|[CAnimationGroup::m\_lstKeyFrames](../Topic/CAnimationGroup::m_lstKeyFrames.md)|Содержит список опорных кадров.|  
|[CAnimationGroup::m\_pStoryboard](../Topic/CAnimationGroup::m_pStoryboard.md)|Указывает на раскадровку анимации.  Этот указатель является действительным только после вызова Animate.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationGroup::m\_nGroupID](../Topic/CAnimationGroup::m_nGroupID.md)|Уникальный идентификатор группы анимации.|  
|[CAnimationGroup::m\_pParentController](../Topic/CAnimationGroup::m_pParentController.md)|Указатель на контроллер анимации, которому принадлежит эта группа.|  
  
## Заметки  
 Группы анимации создаются автоматически контроллером анимации \(CAnimationController\) при добавлении объектов анимации с помощью метода CAnimationController::AddAnimationObject.  Группа анимаций идентифицируется с помощью ИД группы \(GroupID\), который обычно принимается в качестве параметра для манипулирования группами анимаций.  ИД группы берется из первого объекта анимации, добавляемого в новую группу анимации.  Инкапсулированная раскадровка анимации создается после вызова метода CAnimationController::AnimateGroup; доступ к ней осуществляется через общий член m\_pStoryboard.  
  
## Иерархия наследования  
 [CAnimationGroup](../../mfc/reference/canimationgroup-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)