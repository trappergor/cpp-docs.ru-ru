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
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
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
- CAnimationController class
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2cf243c25f14ba016f6f30af264322c658e7322c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="canimationcontroller-class"></a>Класс CAnimationController
Реализует контроллер анимации, который обеспечивает центральный интерфейс для создания анимации и управления ею.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationController : public CObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](#canimationcontroller)|Создает контроллер анимации.|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|Деструктор Вызывается при уничтожении объекта контроллера анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](#addanimationobject)|Добавляет группу, к которой принадлежит контроллер анимации объекта анимации.|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Добавляет группу опорного кадра.|  
|[CAnimationController::AnimateGroup](#animategroup)|Подготавливает группы для запуска анимации и планирует ее при необходимости.|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Перегружен. Вызывается платформой для очистки группе запланированному анимации.|  
|[CAnimationController::CreateKeyframe](#createkeyframe)|Перегружен. Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Задает или освобождает обработчик для вызова при изменении состояния диспетчера анимации.|  
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Задает или освобождает обработчик для события времени и обработчик для времени обновления.|  
|[CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Задает или освобождает приоритет сравнения обработчик для вызова для определения запланированных раскадровки может быть отменена, подтвердила, обрезаются или сжатых.|  
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Задает или освобождает обработчик для событий состояния и обновлении раскадровки.|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Перегружен. Находит группу анимации, его раскадровки.|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|Находит объект анимации, содержащих переменную с указанным анимации.|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Возвращает ключевой кадр, который определяет начало раскадровки.|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Предоставляет доступ к объекту инкапсулированном IUIAnimationManager.|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Предоставляет доступ к объекту инкапсулированном IUIAnimationTimer.|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|Указатель на интерфейс IUIAnimationTransitionFactory или значение NULL, если не удалось создать переход библиотеки.|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Предоставляет доступ к объекту инкапсулированном IUIAnimationTransitionLibrary.|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|Сообщает ли хотя бы одна группа воспроизведения анимации.|  
|[CAnimationController::IsValid](#isvalid)|Указывает, допустимо ли контроллер анимации.|  
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Вызывается инфраструктурой при изменении целочисленное значение переменной анимации.|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Вызывается средой в ответ на событие StatusChanged от диспетчера анимации.|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Вызывается платформой после завершения обновления анимации.|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Вызывается средой перед началом обновления анимации.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Вызывается платформой, когда частота кадров отрисовки для анимации опускается ниже частоту кадров минимальное нежелательно.|  
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|Вызывается инфраструктурой при изменении значения переменной анимации.|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Вызывается платформой вправо до запланированного анимации.|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Вызывается платформой для решения конфликтов планирования.|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Вызывается инфраструктурой при изменении состояния раскадровки.|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Вызывается инфраструктурой при обновлении раскадровки.|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Удаляет все группы анимации из контроллер анимации.|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Удаляет группу анимации с указанным Идентификатором из контроллер анимации.|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Удаление объекта анимации из контроллер анимации.|  
|[CAnimationController::RemoveTransitions](#removetransitions)|Удаляет переходы из анимации объекты, принадлежащие к указанной группы.|  
|[CAnimationController::ScheduleGroup](#schedulegroup)|Планирует анимации.|  
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Устанавливает связь между контроллером анимации и окна.|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Направляет диспетчера анимации, чтобы обновить значения всех переменных анимации.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Перегружен. Вспомогательный класс, который очищает группы.|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Вызывается платформой, когда только что было запланировано анимации для указанной группы.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Опорный кадр, представляющий начало раскадровки.|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|Указывает, является ли контроллер анимации допустимым. Этот член имеет значение FALSE, если текущая операционная система не поддерживает API анимации Windows.|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Список групп анимации, относящиеся к данному контроллеру анимации.|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Хранит указатель на объект COM диспетчера анимации.|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Хранит указатель на объект COM таймера анимации.|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Указатель на связанный объект CWnd можно автоматически перерисовывается при изменении состояния диспетчера анимации или post обновления события. Может иметь значение NULL.|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Хранит указатель перехода фабрики COM-объект.|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Хранит указатель перехода библиотеки COM-объект.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationController является ключевой класс, управляющий анимации. Можно создать один или несколько экземпляров контроллер анимации в приложении и, при необходимости подключите экземпляр контроллер анимации к объекту CWnd, с помощью CAnimationController::SetRelatedWnd. Это подключение требуется для отправки сообщений WM_PAINT связанных окно автоматически при изменении состояния диспетчера анимации или анимации таймер будет обновлен. Если не включить эту связь, должен перерисовать окно, которое отображает анимации вручную. Для этой цели можно создать класс, производный от CAnimationController и переопределить OnAnimationManagerStatusChanged или OnAnimationTimerPostUpdate и одно или несколько окон, при необходимости сделать недействительными.  
  
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
 Добавляет группу, к которой принадлежит контроллер анимации объекта анимации.  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указатель объекта анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на существующую или новую группу анимации, где добавлен pObject, если функция выполняется успешно. Значение NULL, если pObject уже были добавлены в группу, к которой принадлежит другой контроллер анимации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для добавления объекта анимации к контроллеру анимации. Объект будет добавлен к группе в соответствии с GroupID объекта (см. CAnimationBaseObject::SetID). Если это первый объект, добавляемый с указанным GroupID, контроллер анимации создаст новую группу. Объект анимации можно добавить только одна анимация контроллер. Если необходимо добавить объект к другому контроллеру, сначала вызовите RemoveAnimationObject. При вызове метода SetID с новой GroupID для объекта, который уже был добавлен в группу, объект будет удален из старой группе и добавлена в другую группу с указанным идентификатором.  
  
##  <a name="addkeyframetogroup"></a>CAnimationController::AddKeyframeToGroup  
 Добавляет группу опорного кадра.  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `pKeyframe`  
 Указатель опорного кадра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если функция выполнена успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Обычно не нужно вызывать этот метод, используйте CAnimationController::CreateKeyframe, который создает и добавляет созданный ключевой кадр в группу, автоматически.  
  
##  <a name="animategroup"></a>CAnimationController::AnimateGroup  
 Подготавливает группы для запуска анимации и планирует ее при необходимости.  
  
```  
BOOL AnimateGroup(
    UINT32 nGroupID,  
    BOOL bScheduleNow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает GroupID.  
  
 `bScheduleNow`  
 Указывает, следует ли выполнять сразу же анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если анимация был успешно запланированы и выполняются.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняет фактическую работу создания раскадровки, добавление переменных анимации, применения переходов и установки опорных кадров. Возможна задержка календарный план в случае bScheduleNow задано значение FALSE. В этом случае указанная группа будет содержать раскадровку, которые были настроены для анимации. На этом этапе можно настроить события для переменных раскадровки и анимации. Когда необходимо фактически выполнения вызова анимации CAnimationController::ScheduleGroup.  
  
##  <a name="canimationcontroller"></a>CAnimationController::CAnimationController  
 Создает контроллер анимации.  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>CAnimationController::CleanUpGroup  
 Вызывается платформой для очистки группе запланированному анимации.  
  
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
 Задает или освобождает обработчик для вызова при изменении состояния диспетчера анимации.  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, следует ли установить или снять обработчик.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчик был успешно или выпуска.  
  
### <a name="remarks"></a>Примечания  
 Если обработчик установлен (по умолчанию) анимации Windows вызывает OnAnimationManagerStatusChanged при изменении состояния диспетчера анимации.  
  
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
 Задает простое поведение обработчика таймера обновления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчики были успешно или освободить; Значение FALSE, если этот метод вызывается второй раз без освобождения сначала обработчики, или если другие ошибки.  
  
### <a name="remarks"></a>Примечания  
 При обработчики устанавливаются (по умолчанию) вызовы Windows API анимации OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate OnRenderingTooSlow методы. Необходимо включить таймеры анимации разрешить обновление раскадровки анимации Windows API. В противном случае потребуется вызвать CAnimationController::UpdateAnimationManager, чтобы направить анимации manager для обновления значения всех переменных анимации.  
  
##  <a name="enableprioritycomparisonhandler"></a>CAnimationController::EnablePriorityComparisonHandler  
 Задает или освобождает приоритет сравнения обработчик для вызова для определения запланированных раскадровки может быть отменена, подтвердила, обрезаются или сжатых.  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>Параметры  
 `dwHandlerType`  
 Сочетание UI_ANIMATION_PHT_ флагов (см. примечания), которое указывает, какие обработчики, Установка и удаление.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если обработчик был успешно или выпуска.  
  
### <a name="remarks"></a>Примечания  
 Если обработчик установлен (по умолчанию) анимации Windows вызывает следующие виртуальные методы в зависимости от dwHandlerType: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler может быть сочетанием следующих флагов: UI_ANIMATION_PHT_NONE - выпуске все обработчики UI_ANIMATION_PHT_CANCEL - значение "Отмена" Сравнение обработчик UI_ANIMATION_PHT_CONCLUDE - задание обработчика сравнения Conclude UI_ANIMATION_PHT_COMPRESS - задать сжатие сравнения обработчик UI_ANIMATION_PHT_TRIM - набор обработчик Trim сравнения UI_ANIMATION_PHT_CANCEL_REMOVE - удалить обработчик сравнения Отмена UI_ANIMATION_PHT_CONCLUDE_REMOVE - удалить обработчик Conclude сравнения UI_ANIMATION_PHT_COMPRESS_REMOVE - удалить Compress сравнения обработчика UI_ANIMATION_PHT_TRIM_REMOVE - Удаление обработчика Trim сравнения  
  
##  <a name="enablestoryboardeventhandler"></a>CAnimationController::EnableStoryboardEventHandler  
 Задает или освобождает обработчик для событий состояния и обновлении раскадровки.  
  
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
 При задать обработчик (включено) API анимации Windows вызывает OnStoryboardStatusChanges и OnStoryboardUpdated виртуальные методы. Обработчик необходимо задать после вызова CAnimationController::Animate анимации указанной группы, так как она создает инкапсулированный объект IUIAnimationStoryboard.  
  
##  <a name="findanimationgroup"></a>CAnimationController::FindAnimationGroup  
 Находит группу анимации по его идентификатору группы.  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает GroupID.  
  
 `pStoryboard`  
 Указатель раскадровки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на группу анимации или значение NULL, если группа с указанным Идентификатором не найден.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы найти группу анимации во время выполнения. Группа создается и добавляется во внутренний список групп анимации при добавлении первого объекта анимации с конкретной GroupID контроллер анимации.  
  
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
 Вызывается из обработчиков событий, когда это необходимо для поиска объекта анимации из входящего переменной анимации.  
  
##  <a name="g_keyframestoryboardstart"></a>CAnimationController::gkeyframeStoryboardStart  
 Опорный кадр, представляющий начало раскадровки.  
  
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
 Получите этот опорный кадр, чтобы другие ключевые кадры или переходы на момент времени, когда начинается раскадровка.  
  
##  <a name="getuianimationmanager"></a>CAnimationController::GetUIAnimationManager  
 Предоставляет доступ к объекту инкапсулированном IUIAnimationManager.  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUIAnimationManager или значение NULL, если не удалось создать диспетчера анимации.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращает значение FALSE. Может потребоваться доступ к IUIAnimationManager для вызова его методов интерфейса, которые не помещаются в контроллер анимации.  
  
##  <a name="getuianimationtimer"></a>CAnimationController::GetUIAnimationTimer  
 Предоставляет доступ к объекту инкапсулированном IUIAnimationTimer.  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUIAnimationTimer или значение NULL, если не удалось создать таймер анимации.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращает значение FALSE.  
  
##  <a name="getuitransitionfactory"></a>CAnimationController::GetUITransitionFactory  
 Указатель на интерфейс IUIAnimationTransitionFactory или значение NULL, если не удалось создать переход библиотеки.  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на IUIAnimationTransitionFactory или значение NULL, если не удалось создать переход фабрики.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращает значение FALSE.  
  
##  <a name="getuitransitionlibrary"></a>CAnimationController::GetUITransitionLibrary  
 Предоставляет доступ к объекту инкапсулированном IUIAnimationTransitionLibrary.  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUIAnimationTransitionLibrary или значение NULL, если не удалось создать переход библиотеки.  
  
### <a name="remarks"></a>Примечания  
 Если текущая операционная система не поддерживает Windows API анимации, этот метод возвращает значение NULL, и после этого все последующие вызовы CAnimationController::IsValid возвращает значение FALSE.  
  
##  <a name="isanimationinprogress"></a>CAnimationController::IsAnimationInProgress  
 Сообщает ли хотя бы одна группа воспроизведения анимации.  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если анимация выполняется для этого контроллера анимации; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Проверка состояния диспетчера анимации и возвращает значение TRUE, если состояние UI_ANIMATION_MANAGER_BUSY.  
  
##  <a name="isvalid"></a>CAnimationController::IsValid  
 Указывает, допустимо ли контроллер анимации.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если контроллер анимации, являются допустимыми; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение FALSE только в том случае, если анимация Windows API не поддерживается на текущей операционной системы и создание диспетчера анимации не удалось, поскольку он не зарегистрирован. Необходимо вызвать GetUIAnimationManager по крайней мере один раз после инициализации библиотеки COM, чтобы привести значение этого флага.  
  
##  <a name="m_bisvalid"></a>CAnimationController::m_bIsValid  
 Указывает, является ли контроллер анимации допустимым. Этот член имеет значение FALSE, если текущая операционная система не поддерживает API анимации Windows.  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>CAnimationController::m_lstAnimationGroups  
 Список групп анимации, относящиеся к данному контроллеру анимации.  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>CAnimationController::m_pAnimationManager  
 Хранит указатель на объект COM диспетчера анимации.  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>CAnimationController::m_pAnimationTimer  
 Хранит указатель на объект COM таймера анимации.  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>CAnimationController::m_pRelatedWnd  
 Указатель на связанный объект CWnd можно автоматически перерисовывается при изменении состояния диспетчера анимации или post обновления события. Может иметь значение NULL.  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>CAnimationController::m_pTransitionFactory  
 Хранит указатель перехода фабрики COM-объект.  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>CAnimationController::m_pTransitionLibrary  
 Хранит указатель перехода библиотеки COM-объект.  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>CAnimationController::OnAfterSchedule  
 Вызывается платформой, когда только что было запланировано анимации для указанной группы.  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, которая была запланирована.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию удаляет опорные кадры из указанной группы и переходит из анимации переменные, принадлежащие к указанной группе. Можно переопределить в производном классе, чтобы предпринять дополнительные действия на основании расписания анимации.  
  
##  <a name="onanimationintegervaluechanged"></a>CAnimationController::OnAnimationIntegerValueChanged  
 Вызывается инфраструктурой при изменении целочисленное значение переменной анимации.  
  
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
 Указатель на группу анимации, содержащий объекта анимации, значение которого изменилось.  
  
 `pObject`  
 Указатель объекта анимации, который содержит переменную анимации, значение которого изменилось.  
  
 `variable`  
 Указатель на переменную анимации.  
  
 `newValue`  
 Указывает новое значение.  
  
 `prevValue`  
 Указывает предыдущее значение.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при включении события переменной анимации с именем переменной определенного анимации или анимации объекта EnableIntegerValueChangedEvent. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onanimationmanagerstatuschanged"></a>CAnimationController::OnAnimationManagerStatusChanged  
 Вызывается средой в ответ на событие StatusChanged от диспетчера анимации.  
  
```  
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,  
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Параметры  
 `newStatus`  
 Новые состояния диспетчера анимации.  
  
 `previousStatus`  
 Предыдущие состояния диспетчера анимации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена анимация диспетчер событий с EnableAnimationManagerEvent. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Реализация по умолчанию обновляет связанные окна, если он был установлен с SetRelatedWnd.  
  
##  <a name="onanimationtimerpostupdate"></a>CAnimationController::OnAnimationTimerPostUpdate  
 Вызывается платформой после завершения обновления анимации.  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена обработчика событий таймера, с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onanimationtimerpreupdate"></a>CAnimationController::OnAnimationTimerPreUpdate  
 Вызывается средой перед началом обновления анимации.  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена обработчика событий таймера, с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onanimationtimerrenderingtooslow"></a>CAnimationController::OnAnimationTimerRenderingTooSlow  
 Вызывается платформой, когда частота кадров отрисовки для анимации опускается ниже частоту кадров минимальное нежелательно.  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>Параметры  
 `fps`  
 Частоту кадров в кадрах в секунду.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, если включена обработчика событий таймера, с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Частота кадров минимальное желательно указывается путем вызова IUIAnimationTimer::SetFrameRateThreshold.  
  
##  <a name="onanimationvaluechanged"></a>CAnimationController::OnAnimationValueChanged  
 Вызывается инфраструктурой при изменении значения переменной анимации.  
  
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
 Указатель на группу анимации, содержащий объекта анимации, значение которого изменилось.  
  
 `pObject`  
 Указатель объекта анимации, который содержит переменную анимации, значение которого изменилось.  
  
 `variable`  
 Указатель на переменную анимации.  
  
 `newValue`  
 Указывает новое значение.  
  
 `prevValue`  
 Указывает предыдущее значение.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при включении события переменной анимации с именем переменной определенного анимации или анимации объекта EnableValueChangedEvent. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onbeforeanimationstart"></a>CAnimationController::OnBeforeAnimationStart  
 Вызывается платформой вправо до запланированного анимации.  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, анимация является запуск.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов направляется в связанных CWnd и может быть переопределен в производном классе для выполнения дополнительных действий перед запуском анимации для указанной группы.  
  
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
 Вызывается инфраструктурой при изменении состояния раскадровки.  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу анимации, которому принадлежит раскадровки, состояние которого было изменено.  
  
 `newStatus`  
 Указывает новое состояние.  
  
 `previousStatus`  
 Указывает прежнее состояние.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при включении события раскадровки, с помощью CAnimationController::EnableStoryboardEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="onstoryboardupdated"></a>CAnimationController::OnStoryboardUpdated  
 Вызывается инфраструктурой при обновлении раскадровки.  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `pGroup`  
 Указатель на группу, которой принадлежит раскадровки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается при включении события раскадровки, с помощью CAnimationController::EnableStoryboardEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.  
  
##  <a name="removeallanimationgroups"></a>CAnimationController::RemoveAllAnimationGroups  
 Удаляет все группы анимации из контроллер анимации.  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>Примечания  
 Все группы будут удалены, их указатель при сохраняются на уровне приложения, необходимо станет недействительной. Если CAnimationGroup::m_bAutodestroyAnimationObjects для удаляемой группы имеет значение TRUE, будут удалены все объекты анимации, которые входят в эту группу; в противном случае их ссылки на родительский контроллер анимации будет иметь значение NULL и могут быть добавлены к другому контроллеру.  
  
##  <a name="removeanimationgroup"></a>CAnimationController::RemoveAnimationGroup  
 Удаляет группу анимации с указанным Идентификатором из контроллер анимации.  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы анимации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет группу анимации из внутреннего списка групп и удаляет его, поэтому при хранимые указатель в эту группу анимации, его необходимо станет недействительной. Если CAnimationGroup::m_bAutodestroyAnimationObjects имеет значение TRUE, будут удалены все объекты анимации, которые входят в эту группу; в противном случае их ссылки на родительский контроллер анимации будет иметь значение NULL и могут быть добавлены к другому контроллеру.  
  
##  <a name="removeanimationobject"></a>CAnimationController::RemoveAnimationObject  
 Удаление объекта анимации из контроллер анимации.  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указатель объекта анимации.  
  
 `bNoDelete`  
 Если этот параметр имеет значение TRUE объект не удаляется после удаления.  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект анимации из контроллер анимации и группы анимации. Эта функция вызывается в том случае, если не больше анимации определенного объекта или если необходимо переместить объект на другом контроллере анимации. В последнем случае bNoDelete должен иметь значение ИСТИНА.  
  
##  <a name="removetransitions"></a>CAnimationController::RemoveTransitions  
 Удаляет переходы из анимации объекты, принадлежащие к указанной группы.  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы.  
  
### <a name="remarks"></a>Примечания  
 Группы перебирает ее объектов анимации и вызывает ClearTransitions(FALSE) для каждого объекта анимации. Этот метод вызывается платформой после анимации был запланирован.  
  
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
 Значение TRUE, если анимация успешно запланировано. Значение FALSE, если раскадровка не был создан или других ошибок.  
  
### <a name="remarks"></a>Примечания  
 С помощью параметра bScheduleNow равным FALSE предыдущих ScheduleGroup необходимо вызвать AnimateGroup. Можно указать время требуемой анимации, полученные из IUIAnimationTimer::GetTime. Если параметр время равно 0,0, анимация запланирован для текущего времени.  
  
##  <a name="setrelatedwnd"></a>CAnimationController::SetRelatedWnd  
 Устанавливает связь между контроллером анимации и окна.  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на объект окна для задания.  
  
### <a name="remarks"></a>Примечания  
 Если связанный объект CWnd, контроллер анимации можно автоматически обновить (отправить сообщение WM_PAINT) при изменении состояния диспетчера анимации или события таймера post обновления.  
  
##  <a name="updateanimationmanager"></a>CAnimationController::UpdateAnimationManager  
 Направляет диспетчера анимации, чтобы обновить значения всех переменных анимации.  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода перемещает диспетчера анимации на текущее время, внесите необходимые изменения состояния раскадровки и обновление всех переменных анимации соответствующий интерполируются значения. Внутри этого метода вызывает IUIAnimationTimer::GetTime(timeNow) и IUIAnimationManager::Update(timeNow). Переопределите этот метод в производном классе, чтобы изменить это поведение.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

