---
title: "Класс CAnimationController | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
dev_langs:
- C++
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79343615b633b583775a482f0a9d2155e79ede10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="canimationcontroller-class"></a>Класс CAnimationController
Реализует контроллер анимации, который обеспечивает центральный интерфейс для создания анимации и управления ею.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationController : public CObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](#canimationcontroller)|Создает контроллер анимации.|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|Деструктор Вызывается при уничтожении объекта контроллера анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](#addanimationobject)|Добавляет объект анимации в группу, к которой принадлежит контроллер анимации.|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Добавляет группу опорный кадр.|  
|[CAnimationController::AnimateGroup](#animategroup)|Подготавливает группы для выполнения анимации и планирует его при необходимости.|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Перегружен. Вызывается платформой для очистки группе при анимации был запланирован.|  
|[CAnimationController::CreateKeyframe](#createkeyframe)|Перегружен. Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Задает или освобождает обработчик вызывается при изменении состояния диспетчера анимации.|  
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Задает или освобождает обработчик для события времени и обработчик для времени обновления.|  
|[Метода CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Задает или освобождает обработчик сравнения приоритета, вызываемый для определения запланированная раскадровка может быть отменена, подтвердила, усекаются или сжатые.|  
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Задает или освобождает обработчик для события состояния и обновление раскадровки.|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Перегружен. Находит группу анимации, его раскадровки.|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|Находит объект анимации, содержащих переменную с указанным анимации.|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Возвращает ключевой кадр, который определяет начало раскадровки.|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Предоставляет доступ к объекту инкапсулированный IUIAnimationManager.|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Предоставляет доступ к объекту инкапсулированный IUIAnimationTimer.|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|Указатель на интерфейс IUIAnimationTransitionFactory или значение NULL, если не удалось создать библиотеку перехода.|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Предоставляет доступ к объекту инкапсулированный IUIAnimationTransitionLibrary.|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|Указывает, воспроизводится ли хотя бы одна группа анимации.|  
|[CAnimationController::IsValid](#isvalid)|Указывает, является ли допустимым контроллер анимации.|  
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Вызывается платформой при изменении целочисленное значение переменной анимации.|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Вызывается платформой в ответ на событие StatusChanged от диспетчера анимации.|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Вызывается платформой, после завершения обновления анимации.|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Вызывается платформой перед началом обновления анимации.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Вызывается платформой при визуализации частота кадров анимации минимального частоту кадров минимальное нежелательно.|  
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|Вызывается платформой при изменении значения переменной анимации.|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Вызывается платформой вправо до запланированного анимации.|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Вызывается платформой при изменении состояния раскадровки.|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Вызывается платформой при обновлении раскадровки.|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Удаляет все группы анимации с анимацией контроллера.|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Удаляет группу анимации с указанным Идентификатором из контроллер анимации.|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Удалите объекта анимации с анимацией контроллера.|  
|[CAnimationController::RemoveTransitions](#removetransitions)|Удаляет переходы из объектов анимации, принадлежащие к указанной группе.|  
|[CAnimationController::ScheduleGroup](#schedulegroup)|Планирует анимации.|  
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Устанавливает связь между контроллер анимации и окна.|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Направляет диспетчера анимации, чтобы обновить значения всех переменных анимации.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Перегружен. Вспомогательный класс, который очищает группе.|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Вызывается платформой при анимации для указанной группы только что был запланирован.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Ключевой кадр, который представляет запуск раскадровки.|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|Указывает, является ли контроллер анимации допустимым. Этот член имеет значение FALSE, если текущая операционная система не поддерживает API анимации в Windows.|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Список групп анимации, относящиеся к этому контроллеру анимации.|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Содержит указатель на объект COM диспетчера анимации.|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Содержит указатель на COM-таймера анимации объекта.|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Указатель на связанный объект CWnd можно будет перерисовываться автоматически во время возникновения события после обновления или изменение состояния диспетчера анимации. Может иметь значение NULL.|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Содержит указатель на объект COM фабрики перехода.|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Содержит указатель на COM-библиотеки перехода объекта.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationController представляет класс ключа, который управляет анимации. Можно создать один или несколько экземпляров контроллер анимации в приложении и, при необходимости подключения к объекту CWnd, с помощью CAnimationController::SetRelatedWnd экземпляр контроллер анимации. Это подключение, необходимые для автоматической отправки сообщения WM_PAINT связанных окон, при изменении состояния диспетчера анимации или обновлена таймера анимации. Если это отношение не включен, необходимо перерисовать окно, отображающее анимации вручную. Для этой цели можно создать класс, производный от CAnimationController и переопределить OnAnimationManagerStatusChanged и/или OnAnimationTimerPostUpdate и один или несколько периодов, при необходимости сделать недействительными.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationController`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationcontroller"></a>CAnimationController:: ~ CAnimationController  
 Деструктор Вызывается при уничтожении объекта контроллера анимации.  
  
```  
virtual ~CAnimationController(void);
```   
  
##  <a name="addanimationobject"></a>CAnimationController::AddAnimationObject  
 Добавляет объект анимации в группу, к которой принадлежит контроллер анимации.  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указатель на объект анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на существующую или новую группу анимации, которому добавлен pObject, если функция выполняется успешно. Имеет значение NULL, если pObject уже был добавлен в группу, к которой принадлежит другой контроллер анимации.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для добавления объекта анимации контроллер анимации. Объект будет добавлен в группу в соответствии с GroupID объекта (см. CAnimationBaseObject::SetID). Если это первый объект, добавляемый с указанным идентификатором GroupID контроллер анимации создаст новую группу. Только одна анимация контроллеры добавляемыми объекта анимации. Если необходимо добавить объект к другому контроллеру, сначала вызовите RemoveAnimationObject. При вызове метода SetID с новой GroupID для объекта, который уже был добавлен в группу, объект будет удален из старой группе и добавлена в другую группу с указанным идентификатором.  
  
##  <a name="addkeyframetogroup"></a>CAnimationController::AddKeyframeToGroup  
 Добавляет группу опорный кадр.  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `pKeyframe`  
 Указатель опорный кадр.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если функция выполняется успешно. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Обычно не нужно вызывать этот метод, используйте CAnimationController::CreateKeyframe вместо, который создает и автоматически добавляет в группу созданном опорном кадре.  
  
##  <a name="animategroup"></a>CAnimationController::AnimateGroup  
 Подготавливает группы для выполнения анимации и планирует его при необходимости.  
  
```  
BOOL AnimateGroup(
    UINT32 nGroupID,  
    BOOL bScheduleNow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает GroupID.  
  
 `bScheduleNow`  
 Указывает, будет ли выполняться сразу анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если анимация был успешно планируются и выполняются.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняет фактическую работу Создание раскадровки, Добавление анимации переменных, Применение переходов и установка опорных кадров. Возможна задержка планирования, если bScheduleNow задано значение FALSE. В этом случае для указанной группы хранения раскадровки, которые были настроены для анимации. На этом этапе можно настроить события для переменных анимации и раскадровки. Если действительно нужны для выполнения вызова анимации CAnimationController::ScheduleGroup.  
  
##  <a name="canimationcontroller"></a>CAnimationController::CAnimationController  
 Создает контроллер анимации.  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>CAnimationController::CleanUpGroup  
 Вызывается платформой для очистки группе при анимации был запланирован.  
  
```  
void CleanUpGroup(UINT32 nGroupID);  
void CleanUpGroup(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает GroupID.  
  
 `pGroup`  
 Указатель на группу анимации для очистки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все переходы и опорные кадры из указанной группы, так как они не относятся после анимации был запланирован.  
  
##  <a name="createkeyframe"></a>CAnimationController::CreateKeyframe  
 Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.  
  
```  
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,  
    CBaseTransition* pTransition);

 
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Задает идентификатор группы, для которой создается опорный кадр.  
  
 `pTransition`  
 Указатель на переход. Опорный кадр будет вставлен в раскадровку после этого перехода.  
  
 `pKeyframe`  
 Указатель на базовый опорный кадр для данного опорного кадра.  
  
 `offset`  
 Смещение в секундах от базового опорного кадра, заданного параметром pKeyframe.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный опорный кадр, если функция выполнена успешно.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный указатель можно сохранить и основывать другие опорные кадры на только что созданном опорном кадре (см. вторую перегрузку). Можно начинать переходы на опорных кадрах — см. раздел, посвященный CBaseTransition::SetKeyframes. Удалять созданные таким образом опорные кадры не нужно, так как они автоматически удаляются группами анимации. При создании опорных кадров на основе других опорных кадров и переходов будьте внимательны и избегайте циклических ссылок.  
  
##  <a name="enableanimationmanagerevent"></a>CAnimationController::EnableAnimationManagerEvent  
 Задает или освобождает обработчик вызывается при изменении состояния диспетчера анимации.  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, следует ли установить или снять обработчик.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчик был успешно или выпуска.  
  
### <a name="remarks"></a>Примечания  
 Если обработчик установлен (по умолчанию) анимацию Windows вызывает OnAnimationManagerStatusChanged при изменении состояния диспетчера анимации.  
  
##  <a name="enableanimationtimereventhandler"></a>CAnimationController::EnableAnimationTimerEventHandler  
 Задает или освобождает обработчик для события времени и обработчик для времени обновления.  
  
```  
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,  
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, следует ли установить или снять обработчиков.  
  
 `idleBehavior`  
 Задает поведения во время ожидания для обработчика обновлений таймера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчики были успешно или освободить; Значение FALSE, если этот метод вызывается второй раз без освобождения сначала обработчики, или в случае любой другой ошибки.  
  
### <a name="remarks"></a>Примечания  
 При обработчики устанавливаются (по умолчанию) вызовы Windows API анимации OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate OnRenderingTooSlow методы. Необходимо включить анимации таймеры разрешить раскадровки обновления Windows API анимации. В противном случае необходимо вызвать CAnimationController::UpdateAnimationManager, чтобы направить анимации диспетчера, чтобы обновить значения всех переменных анимации.  
  
##  <a name="enableprioritycomparisonhandler"></a>Метода CAnimationController::EnablePriorityComparisonHandler  
 Задает или освобождает обработчик сравнения приоритета, вызываемый для определения запланированная раскадровка может быть отменена, подтвердила, усекаются или сжатые.  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>Параметры  
 `dwHandlerType`  
 Сочетание UI_ANIMATION_PHT_ флаги (см. примечания), которое указывает, какие обработчики установить или снять.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчик был успешно или выпуска.  
  
### <a name="remarks"></a>Примечания  
 Если обработчик установлен (по умолчанию) анимацию Windows вызывает следующие виртуальные методы в зависимости от dwHandlerType: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler может представлять собой сочетание следующих флагов: UI_ANIMATION_PHT_NONE - выпуске все обработчики UI_ANIMATION_PHT_CANCEL - значение "Отмена" обработчик сравнения UI_ANIMATION_PHT_CONCLUDE - задать обработчик сравнения Conclude UI_ANIMATION_PHT_COMPRESS — набор Обработчик сравнения compress UI_ANIMATION_PHT_TRIM - задание обработчика Trim сравнения UI_ANIMATION_PHT_CANCEL_REMOVE - удаление обработчика отмены сравнения UI_ANIMATION_PHT_CONCLUDE_REMOVE - удаление обработчика сравнения Conclude UI_ANIMATION_PHT_COMPRESS_ УДАЛИТЬ — удаление обработчика сравнения Compress UI_ANIMATION_PHT_TRIM_REMOVE - удаление обработчика Trim сравнения  
  
##  <a name="enablestoryboardeventhandler"></a>CAnimationController::EnableStoryboardEventHandler  
 Задает или освобождает обработчик для события состояния и обновление раскадровки.  
  
```  
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `bEnable`  
 Указывает, следует ли установить или снять обработчик.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчик был успешно или освободить; Значение FALSE, если указанная анимация группы теперь находится или не было инициировано анимации для указанной группы и его внутренней раскадровки имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
 При установить обработчик API анимации в Windows (по умолчанию) вызывает OnStoryboardStatusChanges и OnStoryboardUpdated виртуальные методы. Обработчик необходимо задавать после CAnimationController::Animate был вызван для группы указанного анимации, так как она создает инкапсулированный объект IUIAnimationStoryboard.  
  
##  <a name="findanimationgroup"></a>CAnimationController::FindAnimationGroup  
 Находит группу анимации по его идентификатору группы.  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает, является идентификатором GroupID.  
  
 `pStoryboard`  
 Указатель на раскадровку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на группу анимации или значение NULL, если группа с указанным Идентификатором не найдена.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы найти группу анимации во время выполнения. Группы создается и добавляется во внутренний список групп анимации при добавлении первого объекта анимации с определенной GroupID контроллер анимации.  
  
##  <a name="findanimationobject"></a>CAnimationController::FindAnimationObject  
 Находит объект анимации, содержащих переменную с указанным анимации.  
  
```  
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,  
    CAnimationBaseObject** ppObject,  
    CAnimationGroup** ppGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pVariable`  
 Указатель на переменную анимации.  
  
 `ppObject`  
 Выходные данные. Содержит указатель на объект анимации или значение NULL.  
  
 `ppGroup`  
 Выходные данные. Содержит указатель на анимации группа, содержащая объекта анимации, или значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект найден; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Вызывается из обработчиков событий, когда это необходимо для поиска объекта анимации из входящих переменной анимации.  
  
##  <a name="g_keyframestoryboardstart"></a>CAnimationController::gkeyframeStoryboardStart  
 Ключевой кадр, который представляет запуск раскадровки.  
  
```  
static CBaseKeyFrame gkeyframeStoryboardStart;  
```  
  
##  <a name="getkeyframestoryboardstart"></a>CAnimationController::GetKeyframeStoryboardStart  
 Возвращает ключевой кадр, который определяет начало раскадровки.  
  
```  
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на базовый опорный кадр, который определяет начало раскадровки.  
  
### <a name="remarks"></a>Примечания  
 Получите этот опорных кадров на основе других опорных кадров или переходов на момент времени, когда начинается раскадровки.  
  
##  <a name="getuianimationmanager"></a>CAnimationController::GetUIAnimationManager  
 Предоставляет доступ к объекту инкапсулированный IUIAnimationManager.  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUIAnimationManager или значение NULL, если не удалось создать диспетчера анимации.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращаться значение FALSE. Может потребоваться доступ к IUIAnimationManager, чтобы вызывать его методы интерфейса, которые не помещаются в контроллер анимации.  
  
##  <a name="getuianimationtimer"></a>CAnimationController::GetUIAnimationTimer  
 Предоставляет доступ к объекту инкапсулированный IUIAnimationTimer.  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUIAnimationTimer или значение NULL, если сбой создания таймера анимации.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращаться значение FALSE.  
  
##  <a name="getuitransitionfactory"></a>CAnimationController::GetUITransitionFactory  
 Указатель на интерфейс IUIAnimationTransitionFactory или значение NULL, если не удалось создать библиотеку перехода.  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на IUIAnimationTransitionFactory или значение NULL, если не удалось создать переход фабрики.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращаться значение FALSE.  
  
##  <a name="getuitransitionlibrary"></a>CAnimationController::GetUITransitionLibrary  
 Предоставляет доступ к объекту инкапсулированный IUIAnimationTransitionLibrary.  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUIAnimationTransitionLibrary или значение NULL, если не удалось создать библиотеку перехода.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращаться значение FALSE.  
  
##  <a name="isanimationinprogress"></a>CAnimationController::IsAnimationInProgress  
 Указывает, воспроизводится ли хотя бы одна группа анимации.  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если в данный момент для этого контроллера анимации; анимацию в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Проверяет состояния диспетчера анимации и возвращает значение TRUE, если состояние UI_ANIMATION_MANAGER_BUSY.  
  
##  <a name="isvalid"></a>CAnimationController::IsValid  
 Указывает, является ли допустимым контроллер анимации.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если контроллер анимации допустима; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение FALSE, только в том случае, если Windows API анимации не поддерживается в текущей операционной системы и создание диспетчера анимации не удалось, так как он не зарегистрирован. Необходимо вызвать GetUIAnimationManager по крайней мере один раз после инициализации библиотеки COM, чтобы привести значение этого флага.  
  
##  <a name="m_bisvalid"></a>CAnimationController::m_bIsValid  
 Указывает, является ли контроллер анимации допустимым. Этот член имеет значение FALSE, если текущая операционная система не поддерживает API анимации в Windows.  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>CAnimationController::m_lstAnimationGroups  
 Список групп анимации, относящиеся к этому контроллеру анимации.  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>CAnimationController::m_pAnimationManager  
 Содержит указатель на объект COM диспетчера анимации.  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>CAnimationController::m_pAnimationTimer  
 Содержит указатель на COM-таймера анимации объекта.  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>CAnimationController::m_pRelatedWnd  
 Указатель на связанный объект CWnd можно будет перерисовываться автоматически во время возникновения события после обновления или изменение состояния диспетчера анимации. Может иметь значение NULL.  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>CAnimationController::m_pTransitionFactory  
 Содержит указатель на объект COM фабрики перехода.  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>CAnimationController::m_pTransitionLibrary  
 Содержит указатель на COM-библиотеки перехода объекта.  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>CAnimationController::OnAfterSchedule  
 Вызывается платформой при анимации для указанной группы только что был запланирован.  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, который был запланирован.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию удаляет опорные кадры из указанной группы и переходит из анимации переменные, принадлежащие к указанной группе. Можно переопределить в производном классе, чтобы выполнить дополнительные действия на основании расписания анимации.  
  
##  <a name="onanimationintegervaluechanged"></a>CAnimationController::OnAnimationIntegerValueChanged  
 Вызывается платформой при изменении целочисленное значение переменной анимации.  
  
```  
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    INT32 newValue,  
    INT32 prevValue);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, которая содержит объекта анимации, значение которого было изменено.  
  
 `pObject`  
 Указатель на объект анимации, содержащий переменную анимации, значение которого изменилось.  
  
 `variable`  
 Указатель на переменную анимации.  
  
 `newValue`  
 Указывает новое значение.  
  
 `prevValue`  
 Указывает предыдущее значение.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если с именем переменной определенного анимации или анимации объекта EnableIntegerValueChangedEvent включить события переменной анимации. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onanimationmanagerstatuschanged"></a>CAnimationController::OnAnimationManagerStatusChanged  
 Вызывается платформой в ответ на событие StatusChanged от диспетчера анимации.  
  
```  
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,  
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Параметры  
 `newStatus`  
 Новое состояние диспетчера анимации.  
  
 `previousStatus`  
 Предыдущего состояния диспетчера анимации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена анимация диспетчера событий с EnableAnimationManagerEvent. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Реализация по умолчанию обновляет связанные окна, если оно было задано с SetRelatedWnd.  
  
##  <a name="onanimationtimerpostupdate"></a>CAnimationController::OnAnimationTimerPostUpdate  
 Вызывается платформой, после завершения обновления анимации.  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена обработчика событий таймера, с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onanimationtimerpreupdate"></a>CAnimationController::OnAnimationTimerPreUpdate  
 Вызывается платформой перед началом обновления анимации.  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена обработчика событий таймера, с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onanimationtimerrenderingtooslow"></a>CAnimationController::OnAnimationTimerRenderingTooSlow  
 Вызывается платформой при визуализации частота кадров анимации минимального частоту кадров минимальное нежелательно.  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>Параметры  
 `fps`  
 Частоту кадров в кадрах в секунду.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена обработчика событий таймера, с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Частота кадров минимальное желательно указывается путем вызова IUIAnimationTimer::SetFrameRateThreshold.  
  
##  <a name="onanimationvaluechanged"></a>CAnimationController::OnAnimationValueChanged  
 Вызывается платформой при изменении значения переменной анимации.  
  
```  
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    DOUBLE newValue,  
    DOUBLE prevValue);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, которая содержит объекта анимации, значение которого было изменено.  
  
 `pObject`  
 Указатель на объект анимации, содержащий переменную анимации, значение которого изменилось.  
  
 `variable`  
 Указатель на переменную анимации.  
  
 `newValue`  
 Указывает новое значение.  
  
 `prevValue`  
 Указывает предыдущее значение.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если с именем переменной определенного анимации или анимации объекта EnableValueChangedEvent включить события переменной анимации. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onbeforeanimationstart"></a>CAnimationController::OnBeforeAnimationStart  
 Вызывается платформой вправо до запланированного анимации.  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации которого анимация является запуск.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов направляется в связанных CWnd и могут переопределяться в производном классе для выполнения дополнительных действий перед запуском анимации для указанной группы.  
  
##  <a name="onhasprioritycancel"></a>CAnimationController::OnHasPriorityCancel  
 Вызывается платформой для решения конфликтов планирования.  
  
```  
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroupScheduled`  
 Группа, в которую входит текущая запланированная раскадровка.  
  
 `pGroupNew`  
 Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.  
  
 `priorityEffect`  
 Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_CANCEL. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об управлении конфликтами см. в документации по API анимации в Windows (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritycompress"></a>CAnimationController::OnHasPriorityCompress  
 Вызывается платформой для решения конфликтов планирования.  
  
```  
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroupScheduled`  
 Группа, в которую входит текущая запланированная раскадровка.  
  
 `pGroupNew`  
 Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.  
  
 `priorityEffect`  
 Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_COMPRESS. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об управлении конфликтами см. в документации по API анимации в Windows (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhaspriorityconclude"></a>CAnimationController::OnHasPriorityConclude  
 Вызывается платформой для решения конфликтов планирования.  
  
```  
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroupScheduled`  
 Группа, в которую входит текущая запланированная раскадровка.  
  
 `pGroupNew`  
 Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.  
  
 `priorityEffect`  
 Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_CONCLUDE. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об управлении конфликтами см. в документации по API анимации в Windows (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritytrim"></a>CAnimationController::OnHasPriorityTrim  
 Вызывается платформой для решения конфликтов планирования.  
  
```  
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroupScheduled`  
 Группа, в которую входит текущая запланированная раскадровка.  
  
 `pGroupNew`  
 Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.  
  
 `priorityEffect`  
 Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_TRIM. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об управлении конфликтами см. в документации по API анимации в Windows (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onstoryboardstatuschanged"></a>CAnimationController::OnStoryboardStatusChanged  
 Вызывается платформой при изменении состояния раскадровки.  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, которому принадлежит раскадровке, состояние которого было изменено.  
  
 `newStatus`  
 Указывает новое состояние.  
  
 `previousStatus`  
 Указывает прежнее состояние.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включен с помощью CAnimationController::EnableStoryboardEventHandler события раскадровки. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onstoryboardupdated"></a>CAnimationController::OnStoryboardUpdated  
 Вызывается платформой при обновлении раскадровки.  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу, которой принадлежит раскадровке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включен с помощью CAnimationController::EnableStoryboardEventHandler события раскадровки. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="removeallanimationgroups"></a>CAnimationController::RemoveAllAnimationGroups  
 Удаляет все группы анимации с анимацией контроллера.  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>Примечания  
 Все группы, будут удалены, их указателем, если хранятся на уровне приложения, необходимо станут недействительными. Если CAnimationGroup::m_bAutodestroyAnimationObjects для удаления группы имеет значение TRUE, будут удалены все объекты анимации, входящую в эту группу; в противном случае их ссылки на родительский анимации контроллер будет иметь значение NULL, и могут быть добавлены к другому контроллеру.  
  
##  <a name="removeanimationgroup"></a>CAnimationController::RemoveAnimationGroup  
 Удаляет группу анимации с указанным Идентификатором из контроллер анимации.  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы анимации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет группу анимации из внутреннего списка групп и удаляет его, поэтому если вы сохранили указатель в эту группу анимации, его необходимо станут недействительными. Если CAnimationGroup::m_bAutodestroyAnimationObjects имеет значение TRUE, будут удалены все объекты анимации, входящую в эту группу; в противном случае их ссылки на родительский анимации контроллер будет иметь значение NULL, и могут быть добавлены к другому контроллеру.  
  
##  <a name="removeanimationobject"></a>CAnimationController::RemoveAnimationObject  
 Удалите объекта анимации с анимацией контроллера.  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указатель на объект анимации.  
  
 `bNoDelete`  
 Если этот параметр имеет значение TRUE объект не будет удален после удаления.  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект анимации из контроллер анимации и группы анимации. Эта функция вызывается в том случае, если не больше анимации определенного объекта или если необходимо перенести на другой контроллер анимации объекта. В последней bNoDelete вариантов должно быть TRUE.  
  
##  <a name="removetransitions"></a>CAnimationController::RemoveTransitions  
 Удаляет переходы из объектов анимации, принадлежащие к указанной группе.  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы.  
  
### <a name="remarks"></a>Примечания  
 Группа обрабатывает в цикле его анимации объектов и вызывает ClearTransitions(FALSE) для каждого объекта анимации. Этот метод вызывается платформой после анимации был запланирован.  
  
##  <a name="schedulegroup"></a>CAnimationController::ScheduleGroup  
 Планирует анимации.  
  
```  
BOOL ScheduleGroup(
    UINT32 nGroupID,  
    UI_ANIMATION_SECONDS time = 0.0);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы для планирования анимации.  
  
 `time`  
 Указывает время планирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если анимация успешно запланирован. Значение FALSE, если раскадровки не был создан, или других ошибок.  
  
### <a name="remarks"></a>Примечания  
 С помощью параметра bScheduleNow равным FALSE предыдущих ScheduleGroup необходимо вызвать AnimateGroup. Можно указать время требуемой анимации, полученный от IUIAnimationTimer::GetTime. Если параметр времени равен 0,0, анимация запланирована текущее время.  
  
##  <a name="setrelatedwnd"></a>CAnimationController::SetRelatedWnd  
 Устанавливает связь между контроллер анимации и окна.  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на объект window для задания.  
  
### <a name="remarks"></a>Примечания  
 Если связанный объект CWnd, контроллер анимации можно автоматически обновлять его (отправлять сообщения WM_PAINT) при изменении состояния диспетчера анимации или события таймера post обновления.  
  
##  <a name="updateanimationmanager"></a>CAnimationController::UpdateAnimationManager  
 Направляет диспетчера анимации, чтобы обновить значения всех переменных анимации.  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода перемещает диспетчера анимации на текущее время, изменение состояния раскадровок при необходимости и обновление всех переменных анимации соответствующий интерполируются значения. Внутри этого метода вызывает IUIAnimationTimer::GetTime(timeNow) и IUIAnimationManager::Update(timeNow). Переопределите этот метод в производном классе для настройки этого поведения.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
