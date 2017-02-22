---
title: "Класс CAnimationController | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationController"
  - "afxanimationcontroller/CAnimationController"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationController - класс"
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CAnimationController
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует контроллер анимации, который обеспечивает центральный интерфейс для создания анимации и управления ею.  
  
## Синтаксис  
  
```  
class CAnimationController : public CObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationController::CAnimationController](../Topic/CAnimationController::CAnimationController.md)|Создает контроллер анимации.|  
|[CAnimationController::~CAnimationController](../Topic/CAnimationController::~CAnimationController.md)|Деструктор.  Вызывается при уничтожении объекта контроллера анимации.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationController::AddAnimationObject](../Topic/CAnimationController::AddAnimationObject.md)|Добавляет объект анимации в группу, принадлежащую контроллеру анимации.|  
|[CAnimationController::AddKeyframeToGroup](../Topic/CAnimationController::AddKeyframeToGroup.md)|Добавляет опорный кадр в группу.|  
|[CAnimationController::AnimateGroup](../Topic/CAnimationController::AnimateGroup.md)|Подготавливает группу к запуску анимации и \(необязательно\) планирует ее.|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|Перегружен.  Вызывается платформой для очистки группы после того, как анимация запланирована.|  
|[CAnimationController::CreateKeyframe](../Topic/CAnimationController::CreateKeyframe.md)|Перегружен.  Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.|  
|[CAnimationController::EnableAnimationManagerEvent](../Topic/CAnimationController::EnableAnimationManagerEvent.md)|Задает или освобождает обработчик для вызова при изменении состояния диспетчера анимации.|  
|[CAnimationController::EnableAnimationTimerEventHandler](../Topic/CAnimationController::EnableAnimationTimerEventHandler.md)|Задает или освобождает обработчик для временных событий и обработчик для обновлений времени.|  
|[CAnimationController::EnablePriorityComparisonHandler](../Topic/CAnimationController::EnablePriorityComparisonHandler.md)|Устанавливает или освобождает обработчик сравнения приоритета, чтобы определить, может ли запланированная раскадровка быть отменена, завершена, обрезана или сжата.|  
|[CAnimationController::EnableStoryboardEventHandler](../Topic/CAnimationController::EnableStoryboardEventHandler.md)|Устанавливает или освобождает обработчик для событий состояния и обновления раскадровки.|  
|[CAnimationController::FindAnimationGroup](../Topic/CAnimationController::FindAnimationGroup.md)|Перегружен.  Находит группу анимации по ее раскадровке.|  
|[CAnimationController::FindAnimationObject](../Topic/CAnimationController::FindAnimationObject.md)|Находит объект анимации, содержащий заданную переменную анимации.|  
|[CAnimationController::GetKeyframeStoryboardStart](../Topic/CAnimationController::GetKeyframeStoryboardStart.md)|Возвращает опорный кадр, который идентифицирует начало раскадровки.|  
|[CAnimationController::GetUIAnimationManager](../Topic/CAnimationController::GetUIAnimationManager.md)|Предоставляет доступ к инкапсулированному объекту IUIAnimationManager.|  
|[CAnimationController::GetUIAnimationTimer](../Topic/CAnimationController::GetUIAnimationTimer.md)|Предоставляет доступ к инкапсулированному объекту IUIAnimationTimer.|  
|[CAnimationController::GetUITransitionFactory](../Topic/CAnimationController::GetUITransitionFactory.md)|Указатель на интерфейс IUIAnimationTransitionFactory или значение NULL, если создать библиотеку переходов не удалось.|  
|[CAnimationController::GetUITransitionLibrary](../Topic/CAnimationController::GetUITransitionLibrary.md)|Предоставляет доступ к инкапсулированному объекту IUIAnimationTransitionLibrary.|  
|[CAnimationController::IsAnimationInProgress](../Topic/CAnimationController::IsAnimationInProgress.md)|Сообщает, воспроизводит ли хотя бы одна группа анимацию.|  
|[CAnimationController::IsValid](../Topic/CAnimationController::IsValid.md)|Сообщает, допустим ли контроллер анимации.|  
|[CAnimationController::OnAnimationIntegerValueChanged](../Topic/CAnimationController::OnAnimationIntegerValueChanged.md)|Вызывается платформой при изменении целочисленного значения переменной анимации.|  
|[CAnimationController::OnAnimationManagerStatusChanged](../Topic/CAnimationController::OnAnimationManagerStatusChanged.md)|Вызывается платформой в ответ на событие StatusChanged, переданное диспетчером анимации.|  
|[CAnimationController::OnAnimationTimerPostUpdate](../Topic/CAnimationController::OnAnimationTimerPostUpdate.md)|Вызывается платформой по окончании обновления анимации.|  
|[CAnimationController::OnAnimationTimerPreUpdate](../Topic/CAnimationController::OnAnimationTimerPreUpdate.md)|Вызывается платформой до начала обновления анимации.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](../Topic/CAnimationController::OnAnimationTimerRenderingTooSlow.md)|Вызывается платформой, когда частота кадров отрисовки для анимации падает ниже минимальной желаемой частоты кадров.|  
|[CAnimationController::OnAnimationValueChanged](../Topic/CAnimationController::OnAnimationValueChanged.md)|Вызывается платформой при изменении значения переменной анимации.|  
|[CAnimationController::OnBeforeAnimationStart](../Topic/CAnimationController::OnBeforeAnimationStart.md)|Вызывается платформой непосредственно перед планированием анимации.|  
|[CAnimationController::OnHasPriorityCancel](../Topic/CAnimationController::OnHasPriorityCancel.md)|Вызывается платформой для разрешения конфликтов расписания.|  
|[CAnimationController::OnHasPriorityCompress](../Topic/CAnimationController::OnHasPriorityCompress.md)|Вызывается платформой для разрешения конфликтов расписания.|  
|[CAnimationController::OnHasPriorityConclude](../Topic/CAnimationController::OnHasPriorityConclude.md)|Вызывается платформой для разрешения конфликтов расписания.|  
|[CAnimationController::OnHasPriorityTrim](../Topic/CAnimationController::OnHasPriorityTrim.md)|Вызывается платформой для разрешения конфликтов расписания.|  
|[CAnimationController::OnStoryboardStatusChanged](../Topic/CAnimationController::OnStoryboardStatusChanged.md)|Вызывается платформой при изменении состояния раскадровки.|  
|[CAnimationController::OnStoryboardUpdated](../Topic/CAnimationController::OnStoryboardUpdated.md)|Вызывается платформой при обновлении раскадровки.|  
|[CAnimationController::RemoveAllAnimationGroups](../Topic/CAnimationController::RemoveAllAnimationGroups.md)|Удаляет все группы анимации из контроллера анимации.|  
|[CAnimationController::RemoveAnimationGroup](../Topic/CAnimationController::RemoveAnimationGroup.md)|Удаляет группу анимации с заданным ИД из контроллера анимации.|  
|[CAnimationController::RemoveAnimationObject](../Topic/CAnimationController::RemoveAnimationObject.md)|Удаляет объект анимации из контроллера анимации.|  
|[CAnimationController::RemoveTransitions](../Topic/CAnimationController::RemoveTransitions.md)|Удаляет переходы из объектов анимации, принадлежащих к заданной группе.|  
|[CAnimationController::ScheduleGroup](../Topic/CAnimationController::ScheduleGroup.md)|Планирует анимацию.|  
|[CAnimationController::SetRelatedWnd](../Topic/CAnimationController::SetRelatedWnd.md)|Устанавливает отношение между контроллером анимации и окном.|  
|[CAnimationController::UpdateAnimationManager](../Topic/CAnimationController::UpdateAnimationManager.md)|Дает диспетчеру анимации указание обновить значения всех переменных анимации.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|Перегружен.  Вспомогательный метод, очищающий группу.|  
|[CAnimationController::OnAfterSchedule](../Topic/CAnimationController::OnAfterSchedule.md)|Вызывается платформой непосредственно после того, как для заданной группы запланирована анимация.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimationController::g\_KeyframeStoryboardStart](../Topic/CAnimationController::g_KeyframeStoryboardStart.md)|Опорный кадр, представляющий начало раскадровки.|  
|[CAnimationController::m\_bIsValid](../Topic/CAnimationController::m_bIsValid.md)|Указывает, допустим контроллер анимации или нет.  Этот метод имеет значение FALSE, если текущая ОС не поддерживает Windows Animation API.|  
|[CAnimationController::m\_lstAnimationGroups](../Topic/CAnimationController::m_lstAnimationGroups.md)|Список групп анимации, принадлежащих этому контроллеру анимации.|  
|[CAnimationController::m\_pAnimationManager](../Topic/CAnimationController::m_pAnimationManager.md)|Хранит указатель на COM\-объект диспетчера анимации.|  
|[CAnimationController::m\_pAnimationTimer](../Topic/CAnimationController::m_pAnimationTimer.md)|Хранит указатель на COM\-объект таймера анимации.|  
|[CAnimationController::m\_pRelatedWnd](../Topic/CAnimationController::m_pRelatedWnd.md)|Указатель на связанный объект CWnd, который может быть автоматически перерисован при изменении состояния диспетчера анимации или возникновения события после обновления.  Может принимать значение NULL.|  
|[CAnimationController::m\_pTransitionFactory](../Topic/CAnimationController::m_pTransitionFactory.md)|Хранит указатель на COM\-объект фабрики переходов.|  
|[CAnimationController::m\_pTransitionLibrary](../Topic/CAnimationController::m_pTransitionLibrary.md)|Хранит указатель на COM\-объект библиотеки переходов.|  
  
## Заметки  
 Класс CAnimationController — это основной класс, который управляет анимациями.  В приложении можно создать один или несколько экземпляров контроллера анимации и \(необязательно\) связать экземпляр контроллера анимации с объектом CWnd с помощью метода CAnimationController::SetRelatedWnd.  Это соединение необходимо для автоматической отправки сообщений WM\_PAINT в связанное окно при изменении состояния диспетчера анимации или обновлении таймера анимации.  Если это отношение не включено, необходимо перерисовать окно, в котором отображается анимация, вручную.  Для этого можно наследовать класс от класса CAnimationController, переопределить методы OnAnimationManagerStatusChanged и\/или OnAnimationTimerPostUpdate и при необходимости сделать недействительным одно или несколько окон.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationController](../../mfc/reference/canimationcontroller-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)