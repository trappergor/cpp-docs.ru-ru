---
title: Класс CAnimationController
ms.date: 03/27/2019
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
ms.openlocfilehash: 9039d44d9ef36a47c11b3ecaddf232ad427727c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507640"
---
# <a name="canimationcontroller-class"></a>Класс CAnimationController

Реализует контроллер анимации, который обеспечивает центральный интерфейс для создания анимации и управления ею.

## <a name="syntax"></a>Синтаксис

```
class CAnimationController : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Каниматионконтроллер:: Каниматионконтроллер](#canimationcontroller)|Конструирует контроллер анимации.|
|[Каниматионконтроллер:: ~ Каниматионконтроллер](#_dtorcanimationcontroller)|Деструктор Вызывается при уничтожении объекта контроллера анимации.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Каниматионконтроллер:: Адданиматионобжект](#addanimationobject)|Добавляет объект анимации в группу, принадлежащую контроллеру анимации.|
|[Каниматионконтроллер:: Аддкэйфраметограуп](#addkeyframetogroup)|Добавляет опорный кадр в группу.|
|[Каниматионконтроллер:: Аниматеграуп](#animategroup)|Подготавливает группу для запуска анимации и при необходимости планирует ее.|
|[Каниматионконтроллер:: Клеанупграуп](#cleanupgroup)|Перегружен. Вызывается платформой для очистки группы при планировании анимации.|
|[Каниматионконтроллер:: Креатекэйфраме](#createkeyframe)|Перегружен. Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.|
|[Каниматионконтроллер:: Енаблеаниматионманажеревент](#enableanimationmanagerevent)|Задает или освобождает обработчик, который вызывается при изменении состояния диспетчера анимации.|
|[Каниматионконтроллер:: Енаблеаниматионтимеревенсандлер](#enableanimationtimereventhandler)|Задает или освобождает обработчик для временных событий и обработчика для обновлений времени.|
|[Каниматионконтроллер:: Енаблеприоритикомпарисонхандлер](#enableprioritycomparisonhandler)|Задает или освобождает обработчик сравнения приоритетов для вызова, чтобы определить, можно ли отменить запланированную раскадровку, выполнить ее усечение или сжать.|
|[Каниматионконтроллер:: Енаблесторибоардевенсандлер](#enablestoryboardeventhandler)|Задает или освобождает обработчик для событий состояния раскадровки и обновления.|
|[Каниматионконтроллер:: Финданиматионграуп](#findanimationgroup)|Перегружен. Находит группу анимации по раскадровке.|
|[Каниматионконтроллер:: Финданиматионобжект](#findanimationobject)|Находит объект анимации, содержащий указанную переменную анимации.|
|[Каниматионконтроллер:: Жеткэйфраместорибоардстарт](#getkeyframestoryboardstart)|Возвращает опорный кадр, определяющий начало раскадровки.|
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Предоставляет доступ к инкапсулированному объекту Иуианиматионманажер.|
|[Каниматионконтроллер:: Жетуианиматионтимер](#getuianimationtimer)|Предоставляет доступ к инкапсулированному объекту Иуианиматионтимер.|
|[Каниматионконтроллер:: Жетуитранситионфактори](#getuitransitionfactory)|Указатель на интерфейс Иуианиматионтранситионфактори или значение NULL, если создание библиотеки переходов завершилось ошибкой.|
|[Каниматионконтроллер:: Жетуитранситионлибрари](#getuitransitionlibrary)|Предоставляет доступ к инкапсулированному объекту Иуианиматионтранситионлибрари.|
|[Каниматионконтроллер:: Исаниматионинпрогресс](#isanimationinprogress)|Указывает, воспроизводится ли анимация по крайней мере в одной группе.|
|[Каниматионконтроллер:: IsValid](#isvalid)|Указывает, является ли допустимым контроллер анимации.|
|[Каниматионконтроллер:: Онаниматионинтежервалуечанжед](#onanimationintegervaluechanged)|Вызывается платформой при изменении целочисленного значения переменной анимации.|
|[Каниматионконтроллер:: Онаниматионманажерстатусчанжед](#onanimationmanagerstatuschanged)|Вызывается платформой в ответ на событие Статусчанжед из диспетчера анимации.|
|[Каниматионконтроллер:: Онаниматионтимерпоступдате](#onanimationtimerpostupdate)|Вызывается структурой после завершения обновления анимации.|
|[Каниматионконтроллер:: Онаниматионтимерпреупдате](#onanimationtimerpreupdate)|Вызывается платформой перед началом обновления анимации.|
|[Каниматионконтроллер:: Онаниматионтимеррендерингтуслов](#onanimationtimerrenderingtooslow)|Вызывается платформой, когда частота кадров отрисовки для анимации падает ниже минимально желательной частоты кадров.|
|[Каниматионконтроллер:: Онаниматионвалуечанжед](#onanimationvaluechanged)|Вызывается структурой при изменении значения переменной анимации.|
|[Каниматионконтроллер:: Онбефореаниматионстарт](#onbeforeanimationstart)|Вызывается платформой непосредственно перед планированием анимации.|
|[Каниматионконтроллер:: Онхасприоритиканцел](#onhasprioritycancel)|Вызывается платформой для решения конфликтов планирования.|
|[Каниматионконтроллер:: Онхасприоритикомпресс](#onhasprioritycompress)|Вызывается платформой для решения конфликтов планирования.|
|[Каниматионконтроллер:: Онхасприоритиконклуде](#onhaspriorityconclude)|Вызывается платформой для решения конфликтов планирования.|
|[Каниматионконтроллер:: Онхасприорититрим](#onhasprioritytrim)|Вызывается платформой для решения конфликтов планирования.|
|[Каниматионконтроллер:: Онсторибоардстатусчанжед](#onstoryboardstatuschanged)|Вызывается структурой при изменении состояния раскадровки.|
|[Каниматионконтроллер:: Онсторибоардупдатед](#onstoryboardupdated)|Вызывается структурой при обновлении раскадровки.|
|[Каниматионконтроллер:: Ремовеалланиматионграупс](#removeallanimationgroups)|Удаляет все группы анимации из контроллера анимации.|
|[Каниматионконтроллер:: Ремовеаниматионграуп](#removeanimationgroup)|Удаляет группу анимации с указанным ИДЕНТИФИКАТОРом из контроллера анимации.|
|[Каниматионконтроллер:: Ремовеаниматионобжект](#removeanimationobject)|Удаление объекта анимации из контроллера анимации.|
|[Каниматионконтроллер:: Ремоветранситионс](#removetransitions)|Удаляет переходы из объектов анимации, принадлежащих указанной группе.|
|[Каниматионконтроллер:: ScheduleGroup](#schedulegroup)|Планирует анимацию.|
|[Каниматионконтроллер:: Сетрелатедвнд](#setrelatedwnd)|Устанавливает связь между контроллером анимации и окном.|
|[Каниматионконтроллер:: Упдатеаниматионманажер](#updateanimationmanager)|Направляет диспетчеру анимации на обновление значений всех переменных анимации.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[Каниматионконтроллер:: Клеанупграуп](#cleanupgroup)|Перегружен. Вспомогательный объект, очищающий группу.|
|[Каниматионконтроллер:: Онафтерсчедуле](#onafterschedule)|Вызывается структурой при наличии только что запланированной анимации для указанной группы.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Каниматионконтроллер:: Гкэйфраместорибоардстарт](#g_keyframestoryboardstart)|Опорный кадр, представляющий начало раскадровки.|
|[Каниматионконтроллер:: m_bIsValid](#m_bisvalid)|Указывает, является ли контроллер анимации допустимым или нет. Этот член имеет значение FALSE, если текущая ОС не поддерживает API анимации Windows.|
|[Каниматионконтроллер:: m_lstAnimationGroups](#m_lstanimationgroups)|Список групп анимации, принадлежащих данному контроллеру анимации.|
|[Каниматионконтроллер:: m_pAnimationManager](#m_panimationmanager)|Хранит указатель на COM-объект диспетчера анимации.|
|[Каниматионконтроллер:: m_pAnimationTimer](#m_panimationtimer)|Хранит указатель на COM-объект таймера анимации.|
|[Каниматионконтроллер:: m_pRelatedWnd](#m_prelatedwnd)|Указатель на связанный объект CWnd, который можно автоматически перерисовать при изменении состояния диспетчера анимации или при возникновении события POST Update. Может иметь значение NULL.|
|[Каниматионконтроллер:: m_pTransitionFactory](#m_ptransitionfactory)|Хранит указатель на COM-объект фабрики перехода.|
|[Каниматионконтроллер:: m_pTransitionLibrary](#m_ptransitionlibrary)|Хранит указатель на COM-объект библиотеки переходов.|

## <a name="remarks"></a>Примечания

Класс Каниматионконтроллер — это ключевой класс, который управляет анимациями. Вы можете создать один или несколько экземпляров контроллера анимации в приложении и при необходимости подключить экземпляр контроллера анимации к объекту CWnd с помощью Каниматионконтроллер:: Сетрелатедвнд. Это подключение требуется для автоматической отправки сообщений WM_PAINT в соответствующее окно при изменении состояния диспетчера анимации или при обновлении таймера анимации. Если это отношение не включено, необходимо перерисовать окно, которое отображает анимацию вручную. Для этого можно создать производный класс от Каниматионконтроллер и переопределить Онаниматионманажерстатусчанжед и/или Онаниматионтимерпоступдате и сделать недействительным одно или несколько окон при необходимости.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="_dtorcanimationcontroller"></a>Каниматионконтроллер:: ~ Каниматионконтроллер

Деструктор Вызывается при уничтожении объекта контроллера анимации.

```
virtual ~CAnimationController(void);
```

##  <a name="addanimationobject"></a>Каниматионконтроллер:: Адданиматионобжект

Добавляет объект анимации в группу, принадлежащую контроллеру анимации.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>Параметры

*Объект*<br/>
Указатель на объект анимации.

### <a name="return-value"></a>Возвращаемое значение

Указатель на существующую или новую группу анимации, где объект был добавлен, если функция выполнена успешно; Значение NULL, если объект уже добавлен в группу, принадлежащую другому контроллеру анимации.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы добавить объект анимации в контроллер анимации. Объект будет добавлен в группу в соответствии с объектом GroupID (см. Каниматионбасеобжект:: Сетид). Контроллер анимации создаст новую группу, если это первый объект, добавляемый с указанным GroupID. Объект анимации можно добавить только в один контроллер анимации. Если необходимо добавить объект в другой контроллер, сначала вызовите Ремовеаниматионобжект. При вызове Сетид с новым GroupID для объекта, уже добавленного в группу, объект будет удален из старой группы и добавлен в другую группу с указанным ИДЕНТИФИКАТОРом.

##  <a name="addkeyframetogroup"></a>Каниматионконтроллер:: Аддкэйфраметограуп

Добавляет опорный кадр в группу.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает идентификатор группы.

*Заданного параметром pKeyframe*<br/>
Указатель на опорный кадр.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если функция выполнена. в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Обычно вызывать этот метод не нужно, вместо этого следует использовать Каниматионконтроллер:: Креатекэйфраме, который создает и добавляет созданный опорный кадр в группу автоматически.

##  <a name="animategroup"></a>Каниматионконтроллер:: Аниматеграуп

Подготавливает группу для запуска анимации и при необходимости планирует ее.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает GroupID.

*бсчедуленов*<br/>
Указывает, следует ли сразу же запускать анимацию.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если анимация успешно запланирована и выполнена.

### <a name="remarks"></a>Примечания

Этот метод выполняет фактическую работу по созданию раскадровки, добавляя переменные анимации, применение переходов и настройку опорных кадров. Можно отложить планирование, если для Бсчедуленов задано значение FALSE. В этом случае указанная группа будет содержать раскадровку, настроенную для анимации. На этом этапе можно настроить события для переменных Storyboard и Animation. При необходимости запустите анимацию Call Каниматионконтроллер:: ScheduleGroup.

##  <a name="canimationcontroller"></a>Каниматионконтроллер:: Каниматионконтроллер

Конструирует контроллер анимации.

```
CAnimationController(void);
```

##  <a name="cleanupgroup"></a>Каниматионконтроллер:: Клеанупграуп

Вызывается платформой для очистки группы при планировании анимации.

```
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает GroupID.

*пграуп*<br/>
Указатель на группу анимации для очистки.

### <a name="remarks"></a>Примечания

Этот метод удаляет все переходы и опорные кадры из указанной группы, поскольку они не важны после запланированной анимации.

##  <a name="createkeyframe"></a>Каниматионконтроллер:: Креатекэйфраме

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

*нграупид*<br/>
Задает идентификатор группы, для которой создается опорный кадр.

*птранситион*<br/>
Указатель на переход. Опорный кадр будет вставлен в раскадровку после этого перехода.

*Заданного параметром pKeyframe*<br/>
Указатель на базовый опорный кадр для данного опорного кадра.

*offset*<br/>
Смещение в секундах от базового опорного кадра, заданного параметром pKeyframe.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный опорный кадр, если функция выполнена успешно.

### <a name="remarks"></a>Примечания

Возвращенный указатель можно сохранить и основывать другие опорные кадры на только что созданном опорном кадре (см. вторую перегрузку). Можно начинать переходы на опорных кадрах — см. раздел, посвященный CBaseTransition::SetKeyframes. Удалять созданные таким образом опорные кадры не нужно, так как они автоматически удаляются группами анимации. При создании опорных кадров на основе других опорных кадров и переходов будьте внимательны и избегайте циклических ссылок.

##  <a name="enableanimationmanagerevent"></a>Каниматионконтроллер:: Енаблеаниматионманажеревент

Задает или освобождает обработчик, который вызывается при изменении состояния диспетчера анимации.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, следует ли устанавливать или освобождать обработчик.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если обработчик был успешно установлен или освобожден.

### <a name="remarks"></a>Примечания

Если обработчик задан (включен), то анимация Windows вызывает Онаниматионманажерстатусчанжед при изменении состояния диспетчера анимации.

##  <a name="enableanimationtimereventhandler"></a>Каниматионконтроллер:: Енаблеаниматионтимеревенсандлер

Задает или освобождает обработчик для временных событий и обработчика для обновлений времени.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, следует ли устанавливать или освобождать обработчики.

*идлебехавиор*<br/>
Задает поведение при простое обработчика обновления таймера.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если обработчики успешно заданы или освобождены; Значение FALSE, если этот метод вызывается во второй раз, не освобождая обработчики первыми, или при возникновении любой другой ошибки.

### <a name="remarks"></a>Примечания

Если обработчики заданы (включены) API анимации Windows вызывает методы Онаниматионтимерпреупдате, Онаниматионтимерпоступдате, Онрендерингтуслов. Необходимо включить таймеры анимации, чтобы разрешить обновление раскадровок API анимации Windows. В противном случае необходимо вызвать метод Каниматионконтроллер:: Упдатеаниматионманажер, чтобы направить диспетчеру анимации на обновление значений всех переменных анимации.

##  <a name="enableprioritycomparisonhandler"></a>Каниматионконтроллер:: Енаблеприоритикомпарисонхандлер

Задает или освобождает обработчик сравнения приоритетов для вызова, чтобы определить, можно ли отменить запланированную раскадровку, выполнить ее усечение или сжать.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>Параметры

*двхандлертипе*<br/>
Сочетание флагов UI_ANIMATION_PHT_ (см. примечания), которое указывает, какие обработчики следует задавать или выпустить.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если обработчик был успешно установлен или освобожден.

### <a name="remarks"></a>Примечания

Если обработчик задан (включен), то анимация Windows вызывает следующие виртуальные методы в зависимости от Двхандлертипе: Онхасприоритиканцел, Онхасприоритиконклуде, Онхасприорититрим, Онхасприоритикомпресс. Двхандлер может быть сочетанием следующих флагов: UI_ANIMATION_PHT_NONE — освобождение всех обработчиков UI_ANIMATION_PHT_CANCEL. Set отмена обработчика сравнения UI_ANIMATION_PHT_CONCLUDE — Set заключительный обработчик сравнения UI_ANIMATION_PHT_COMPRESS-Set обработчик сравнения сжатия UI_ANIMATION_PHT_TRIM-Set Обработчик сравнения Trim UI_ANIMATION_PHT_CANCEL_REMOVE-Remove отмена обработчика сравнения UI_ANIMATION_PHT_CONCLUDE_REMOVE-Remove заключительный обработчик сравнения UI_ANIMATION_PHT_COMPRESS_REMOVE-Remove сжимать Handler UI_ANIMATION_PHT _TRIM_REMOVE-удалить обработчик сравнения усечений

##  <a name="enablestoryboardeventhandler"></a>Каниматионконтроллер:: Енаблесторибоардевенсандлер

Задает или освобождает обработчик для событий состояния раскадровки и обновления.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает идентификатор группы.

*bEnable*<br/>
Указывает, следует ли устанавливать или освобождать обработчик.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если обработчик был успешно установлен или освобожден; Значение FALSE, если указанная группа анимации уже найдена или анимация для указанной группы не была инициирована, а ее внутренняя раскадровка имеет значение NULL.

### <a name="remarks"></a>Примечания

Если обработчик задан (включен), API анимации Windows вызывает виртуальные методы Онсторибоардстатусчанжес и Онсторибоардупдатед. Обработчик должен быть установлен после вызова Каниматионконтроллер:: Animation для указанной группы анимации, так как он создает инкапсулированный объект Иуианиматионсторибоард.

##  <a name="findanimationgroup"></a>Каниматионконтроллер:: Финданиматионграуп

Находит группу анимации по ее ИДЕНТИФИКАТОРу группы.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает GroupID.

*псторибоард*<br/>
Указатель на раскадровку.

### <a name="return-value"></a>Возвращаемое значение

Указатель на группу анимации или значение NULL, если группа с указанным ИДЕНТИФИКАТОРом не найдена.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы найти группу анимации во время выполнения. Группа создается и добавляется во внутренний список групп анимации при добавлении в контроллер анимации первого объекта анимации с определенным GroupID.

##  <a name="findanimationobject"></a>Каниматионконтроллер:: Финданиматионобжект

Находит объект анимации, содержащий указанную переменную анимации.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>Параметры

*пвариабле*<br/>
Указатель на переменную анимации.

*ппобжект*<br/>
Проверки. Содержит указатель на объект анимации или значение NULL.

*ппграуп*<br/>
Проверки. Содержит указатель на группу анимации, содержащую объект анимации, или значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект найден; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Вызывается из обработчиков событий, когда требуется найти объект анимации из входящей переменной анимации.

##  <a name="g_keyframestoryboardstart"></a>Каниматионконтроллер:: Гкэйфраместорибоардстарт

Опорный кадр, представляющий начало раскадровки.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

##  <a name="getkeyframestoryboardstart"></a>Каниматионконтроллер:: Жеткэйфраместорибоардстарт

Возвращает опорный кадр, определяющий начало раскадровки.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый опорный кадр, определяющий начало раскадровки.

### <a name="remarks"></a>Примечания

Получите этот ключевой кадр, чтобы основывать любые другие опорные кадры или переходы на момент времени, когда начинается раскадровка.

##  <a name="getuianimationmanager"></a>Каниматионконтроллер:: Жетуианиматионманажер

Предоставляет доступ к инкапсулированному объекту Иуианиматионманажер.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс Иуианиматионманажер или значение NULL, если создание диспетчера анимации завершилось сбоем.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает значение NULL и после того, как все последующие вызовы метода Каниматионконтроллер:: IsValid возвращают значение FALSE. Для вызова методов интерфейса, которые не упакованы в контроллер анимации, может потребоваться доступ к Иуианиматионманажер.

##  <a name="getuianimationtimer"></a>Каниматионконтроллер:: Жетуианиматионтимер

Предоставляет доступ к инкапсулированному объекту Иуианиматионтимер.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс Иуианиматионтимер или значение NULL, если создание таймера анимации завершилось сбоем.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает значение NULL и после того, как все последующие вызовы метода Каниматионконтроллер:: IsValid возвращают значение FALSE.

##  <a name="getuitransitionfactory"></a>Каниматионконтроллер:: Жетуитранситионфактори

Указатель на интерфейс Иуианиматионтранситионфактори или значение NULL, если создание библиотеки переходов завершилось ошибкой.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на Иуианиматионтранситионфактори или значение NULL, если создание фабрики переходов завершилось сбоем.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает значение NULL и после того, как все последующие вызовы метода Каниматионконтроллер:: IsValid возвращают значение FALSE.

##  <a name="getuitransitionlibrary"></a>Каниматионконтроллер:: Жетуитранситионлибрари

Предоставляет доступ к инкапсулированному объекту Иуианиматионтранситионлибрари.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс Иуианиматионтранситионлибрари или значение NULL, если создание библиотеки переходов завершилось ошибкой.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает значение NULL и после того, как все последующие вызовы метода Каниматионконтроллер:: IsValid возвращают значение FALSE.

##  <a name="isanimationinprogress"></a>Каниматионконтроллер:: Исаниматионинпрогресс

Указывает, воспроизводится ли анимация по крайней мере в одной группе.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если для этого контроллера анимации выполняется анимация; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Проверяет состояние диспетчера анимации и возвращает значение TRUE, если состояние — UI_ANIMATION_MANAGER_BUSY.

##  <a name="isvalid"></a>Каниматионконтроллер:: IsValid

Указывает, является ли допустимым контроллер анимации.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если контроллер анимации допустим; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение FALSE, только если API анимации Windows не поддерживается в текущей ОС и не удалось создать диспетчер анимации, так как он не зарегистрирован. Необходимо вызвать Жетуианиматионманажер по крайней мере один раз после инициализации библиотек COM, чтобы установить этот флаг.

##  <a name="m_bisvalid"></a>Каниматионконтроллер:: m_bIsValid

Указывает, является ли контроллер анимации допустимым или нет. Этот член имеет значение FALSE, если текущая ОС не поддерживает API анимации Windows.

```
BOOL m_bIsValid;
```

##  <a name="m_lstanimationgroups"></a>Каниматионконтроллер:: m_lstAnimationGroups

Список групп анимации, принадлежащих данному контроллеру анимации.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

##  <a name="m_panimationmanager"></a>Каниматионконтроллер:: m_pAnimationManager

Хранит указатель на COM-объект диспетчера анимации.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

##  <a name="m_panimationtimer"></a>Каниматионконтроллер:: m_pAnimationTimer

Хранит указатель на COM-объект таймера анимации.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

##  <a name="m_prelatedwnd"></a>Каниматионконтроллер:: m_pRelatedWnd

Указатель на связанный объект CWnd, который можно автоматически перерисовать при изменении состояния диспетчера анимации или при возникновении события POST Update. Может иметь значение NULL.

```
CWnd* m_pRelatedWnd;
```

##  <a name="m_ptransitionfactory"></a>Каниматионконтроллер:: m_pTransitionFactory

Хранит указатель на COM-объект фабрики перехода.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

##  <a name="m_ptransitionlibrary"></a>Каниматионконтроллер:: m_pTransitionLibrary

Хранит указатель на COM-объект библиотеки переходов.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

##  <a name="onafterschedule"></a>Каниматионконтроллер:: Онафтерсчедуле

Вызывается структурой при наличии только что запланированной анимации для указанной группы.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*пграуп*<br/>
Указатель на группу анимации, которая была запланирована.

### <a name="remarks"></a>Примечания

Реализация по умолчанию удаляет опорные кадры из указанной группы и переходит от переменных анимации, принадлежащих указанной группе. Может быть переопределен в производном классе для выполнения дополнительных действий по расписанию анимации.

##  <a name="onanimationintegervaluechanged"></a>Каниматионконтроллер:: Онаниматионинтежервалуечанжед

Вызывается платформой при изменении целочисленного значения переменной анимации.

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>Параметры

*пграуп*<br/>
Указатель на группу анимации, содержащую объект анимации, значение которого изменилось.

*Объект*<br/>
Указатель на объект анимации, содержащий переменную анимации, значение которой изменилось.

*перемен*<br/>
Указатель на переменную анимации.

*newValue*<br/>
Указывает новое значение.

*преввалуе*<br/>
Указывает предыдущее значение.

### <a name="remarks"></a>Примечания

Этот метод вызывается при включении событий переменной анимации с Енаблеинтежервалуечанжедевент, вызываемым для конкретной переменной анимации или объекта анимации. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

##  <a name="onanimationmanagerstatuschanged"></a>Каниматионконтроллер:: Онаниматионманажерстатусчанжед

Вызывается платформой в ответ на событие Статусчанжед из диспетчера анимации.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Параметры

*невстатус*<br/>
Новое состояние диспетчера анимации.

*превиаусстатус*<br/>
Предыдущее состояние диспетчера анимации.

### <a name="remarks"></a>Примечания

Этот метод вызывается при включении событий диспетчера анимации с помощью Енаблеаниматионманажеревент. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Реализация по умолчанию обновляет связанное окно, если оно задано с помощью Сетрелатедвнд.

##  <a name="onanimationtimerpostupdate"></a>Каниматионконтроллер:: Онаниматионтимерпоступдате

Вызывается структурой после завершения обновления анимации.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включили обработчики событий таймера с помощью Енаблеаниматионтимеревенсандлер. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

##  <a name="onanimationtimerpreupdate"></a>Каниматионконтроллер:: Онаниматионтимерпреупдате

Вызывается платформой перед началом обновления анимации.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включили обработчики событий таймера с помощью Енаблеаниматионтимеревенсандлер. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

##  <a name="onanimationtimerrenderingtooslow"></a>Каниматионконтроллер:: Онаниматионтимеррендерингтуслов

Вызывается платформой, когда частота кадров отрисовки для анимации падает ниже минимально желательной частоты кадров.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>Параметры

*частота*<br/>
Текущая частота кадров в кадрах в секунду.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включили обработчики событий таймера с помощью Енаблеаниматионтимеревенсандлер. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Минимальная требуемая частота кадров указывается путем вызова Иуианиматионтимер:: Сетфрамератесрешолд.

##  <a name="onanimationvaluechanged"></a>Каниматионконтроллер:: Онаниматионвалуечанжед

Вызывается структурой при изменении значения переменной анимации.

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>Параметры

*пграуп*<br/>
Указатель на группу анимации, содержащую объект анимации, значение которого изменилось.

*Объект*<br/>
Указатель на объект анимации, содержащий переменную анимации, значение которой изменилось.

*перемен*<br/>
Указатель на переменную анимации.

*newValue*<br/>
Указывает новое значение.

*преввалуе*<br/>
Указывает предыдущее значение.

### <a name="remarks"></a>Примечания

Этот метод вызывается при включении событий переменной анимации с Енаблевалуечанжедевент, вызываемым для конкретной переменной анимации или объекта анимации. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

##  <a name="onbeforeanimationstart"></a>Каниматионконтроллер:: Онбефореаниматионстарт

Вызывается платформой непосредственно перед планированием анимации.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*пграуп*<br/>
Указатель на группу анимации, для которой начинается анимация.

### <a name="remarks"></a>Примечания

Этот вызов направляется в связанный CWnd и может быть переопределен в производном классе для выполнения дополнительных действий до начала анимации для указанной группы.

##  <a name="onhasprioritycancel"></a>Каниматионконтроллер:: Онхасприоритиканцел

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*пграупсчедулед*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*пграупнев*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*приоритеффект*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_CANCEL. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об [управлении конфликтами](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)см. в документации по API анимации Windows.

##  <a name="onhasprioritycompress"></a>Каниматионконтроллер:: Онхасприоритикомпресс

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*пграупсчедулед*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*пграупнев*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*приоритеффект*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_COMPRESS. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об [управлении конфликтами](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)см. в документации по API анимации Windows.

##  <a name="onhaspriorityconclude"></a>Каниматионконтроллер:: Онхасприоритиконклуде

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*пграупсчедулед*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*пграупнев*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*приоритеффект*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_CONCLUDE. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об [управлении конфликтами](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)см. в документации по API анимации Windows.

##  <a name="onhasprioritytrim"></a>Каниматионконтроллер:: Онхасприорититрим

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*пграупсчедулед*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*пграупнев*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*приоритеффект*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_TRIM. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Дополнительные сведения об [управлении конфликтами](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)см. в документации по API анимации Windows.

##  <a name="onstoryboardstatuschanged"></a>Каниматионконтроллер:: Онсторибоардстатусчанжед

Вызывается структурой при изменении состояния раскадровки.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Параметры

*пграуп*<br/>
Указатель на группу анимации, которой принадлежит раскадровка, состояние которой изменилось.

*невстатус*<br/>
Указывает новое состояние.

*превиаусстатус*<br/>
Указывает предыдущее состояние.

### <a name="remarks"></a>Примечания

Этот метод вызывается при включении событий раскадровки с помощью Каниматионконтроллер:: Енаблесторибоардевенсандлер. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

##  <a name="onstoryboardupdated"></a>Каниматионконтроллер:: Онсторибоардупдатед

Вызывается структурой при обновлении раскадровки.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*пграуп*<br/>
Указатель на группу, которой принадлежит раскадровка.

### <a name="remarks"></a>Примечания

Этот метод вызывается при включении событий раскадровки с помощью Каниматионконтроллер:: Енаблесторибоардевенсандлер. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

##  <a name="removeallanimationgroups"></a>Каниматионконтроллер:: Ремовеалланиматионграупс

Удаляет все группы анимации из контроллера анимации.

```
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>Примечания

Все группы будут удалены, и их указатель, если он хранится на уровне приложения, должен быть недействительным. Если CAnimationGroup:: m_bAutodestroyAnimationObjects для удаляемой группы имеет значение TRUE, все объекты анимации, принадлежащие к этой группе, будут удалены. в противном случае для ссылок на родительский контроллер анимации будет задано значение NULL, и их можно будет добавить к другому контроллеру.

##  <a name="removeanimationgroup"></a>Каниматионконтроллер:: Ремовеаниматионграуп

Удаляет группу анимации с указанным ИДЕНТИФИКАТОРом из контроллера анимации.

```
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает идентификатор группы анимации.

### <a name="remarks"></a>Примечания

Этот метод удаляет группу анимации из внутреннего списка групп и удаляет ее, поэтому, если вы сохранили указатель на эту группу анимации, она должна быть аннулирована. Если CAnimationGroup:: m_bAutodestroyAnimationObjects имеет значение TRUE, все объекты анимации, принадлежащие к этой группе, будут удалены. в противном случае для ссылок на родительский контроллер анимации будет задано значение NULL, и их можно будет добавить к другому контроллеру.

##  <a name="removeanimationobject"></a>Каниматионконтроллер:: Ремовеаниматионобжект

Удаление объекта анимации из контроллера анимации.

```
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>Параметры

*Объект*<br/>
Указатель на объект анимации.

*бноделете*<br/>
Если этот параметр имеет значение TRUE, объект не будет удален после удаления.

### <a name="remarks"></a>Примечания

Удаляет объект анимации из контроллера анимации и группы анимации. Вызывайте эту функцию, если определенный объект больше не должен быть анимирован, или если необходимо переместить объект в другой контроллер анимации. В последнем случае Бноделете должно иметь значение TRUE.

##  <a name="removetransitions"></a>Каниматионконтроллер:: Ремоветранситионс

Удаляет переходы из объектов анимации, принадлежащих указанной группе.

```
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Указывает идентификатор группы.

### <a name="remarks"></a>Примечания

Группа выполняет перебор объектов анимации и вызывает Клеартранситионс (FALSE) для каждого объекта анимации. Этот метод вызывается платформой после запланированной анимации.

##  <a name="schedulegroup"></a>Каниматионконтроллер:: ScheduleGroup

Планирует анимацию.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>Параметры

*нграупид*<br/>
Задает для расписания идентификатор группы анимации.

*time*<br/>
Указывает время для расписания.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если анимация была успешно запланирована. Значение FALSE, если раскадровка не была создана, или возникла другая ошибка.

### <a name="remarks"></a>Примечания

Необходимо вызвать Аниматеграуп с параметром Бсчедуленов, имеющим значение FALSE перед ScheduleGroup. Вы можете указать нужное время анимации, полученное от Иуианиматионтимер:: Time. Если параметр времени равен 0,0, то анимация запланирована на текущее время.

##  <a name="setrelatedwnd"></a>Каниматионконтроллер:: Сетрелатедвнд

Устанавливает связь между контроллером анимации и окном.

```
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на заданный объект окна.

### <a name="remarks"></a>Примечания

Если установлен связанный объект CWnd, контроллер анимации может автоматически обновить его (отправить сообщение WM_PAINT) при изменении состояния диспетчера анимации или при возникновении события таймера после обновления.

##  <a name="updateanimationmanager"></a>Каниматионконтроллер:: Упдатеаниматионманажер

Направляет диспетчеру анимации на обновление значений всех переменных анимации.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>Примечания

При вызове этого метода диспетчер анимации перемещается к текущему времени, изменяются состояния раскадровки по мере необходимости и обновляются все переменные анимации с соответствующими значениями интерполяции. Внутренний метод вызывает Иуианиматионтимер::-Time (Тименов) и Иуианиматионманажер:: Update (Тименов). Переопределите этот метод в производном классе, чтобы настроить это поведение.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
