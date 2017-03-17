---
title: "Класс CAnimationGroup | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationGroup class
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a59d8a86fde68510d48e4a3398b6590b2215cbea
ms.lasthandoff: 02/24/2017

---
# <a name="canimationgroup-class"></a>Класс CAnimationGroup
Реализует группу анимации, которая объединяет раскадровку анимации, объекты анимации и переходы, определяющие анимацию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationGroup;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Создает группу анимации.|  
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|Деструктор Вызывается при уничтожении группу анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationGroup::Animate](#animate)|Анимируется группы.|  
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Применяет переходы для объектов анимации.|  
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Выполняет поиск объекта анимации, содержащий переменную указанного анимации.|  
|[CAnimationGroup::GetGroupID](#getgroupid)|Возвращает GroupID.|  
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Удаляет и при необходимости уничтожает все ключевые кадры, которые принадлежат группе анимации.|  
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Удаляет переходы из объекта анимации, которые принадлежат группе анимации.|  
|[CAnimationGroup::Schedule](#schedule)|Планирует анимации в указанное время.|  
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Указывает, что переходы уничтожить всех объектов анимации, которые принадлежат группе автоматически.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Вспомогательный класс, добавляющий опорные кадры для раскадровки.|  
|[CAnimationGroup::AddTransitions](#addtransitions)|Вспомогательный класс, добавляющий переходы в раскадровку.|  
|[CAnimationGroup::CreateTransitions](#createtransitions)|Вспомогательный класс, создающий объекты COM перехода.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Указывает, как очистить переходы из анимации объектов, принадлежащих группе. Если этот элемент имеет значение TRUE, переходы будут удалены автоматически запланированному анимации. В противном случае необходимо вручную удалить переходы.|  
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Указывает, как для уничтожения объектов анимации. Если этот параметр имеет значение TRUE, объекты анимации будут уничтожены автоматически при удалении группы. В противном случае объекты анимации необходимо удалить вручную. Значение по умолчанию — FALSE. Это значение равно TRUE только в том случае, если все объекты анимации, которые принадлежат группе выделяется динамически с помощью оператора new.|  
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Указывает способ удаления ключевых кадров. Если это значение равно TRUE, все ключевые кадры удаляются и уничтожено; в противном случае они удаляются только из списка. Значение по умолчанию — TRUE.|  
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Содержит список объектов анимации.|  
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Содержит список ключевых кадров.|  
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Указывает раскадровки анимации. Этот указатель является действительным только после вызова на анимировать.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Уникальный идентификатор группы анимации.|  
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Указатель на контроллер анимации, к которой принадлежит эта группа.|  
  
## <a name="remarks"></a>Примечания  
 Анимация группы создаются автоматически контроллер анимации (CAnimationController) при добавлении объектов анимации с помощью CAnimationController::AddAnimationObject. Анимация группа определяется GroupID, которая обычно рассматривается как параметр для управления группами анимации. GroupID берется из первого объекта анимации, добавляемый в новую группу анимации. Раскадровку анимации инкапсулированный создается после вызова CAnimationController::AnimateGroup и может осуществляться через m_pStoryboard открытый член.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAnimationGroup`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationgroup"></a>CAnimationGroup:: ~ CAnimationGroup  
 Деструктор Вызывается при уничтожении группу анимации.  
  
```  
~CAnimationGroup();
```  
  
##  <a name="addkeyframes"></a>CAnimationGroup::AddKeyframes  
 Вспомогательный класс, добавляющий опорные кадры для раскадровки.  
  
```  
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на объект COM раскадровки.  
  
 `bAddDeep`  
 Указывает, является ли этот метод следует добавить раскадровки опорные кадры, которые зависят от других опорных кадрах.  
  
##  <a name="addtransitions"></a>CAnimationGroup::AddTransitions  
 Вспомогательный класс, добавляющий переходы в раскадровку.  
  
```  
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на объект COM раскадровки.  
  
 `bDependOnKeyframes`  
  
##  <a name="animate"></a>CAnimationGroup::Animate  
 Анимируется группы.  
  
```  
BOOL Animate(
    IUIAnimationManager* pManager,  
    IUIAnimationTimer* pTimer,  
    BOOL bScheduleNow);
```  
  
### <a name="parameters"></a>Параметры  
 `pManager`  
 `pTimer`  
 `bScheduleNow`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает внутренний раскадровки, создает и применяет переходов и планирует анимации, если bScheduleNow имеет значение TRUE. Если bScheduleNow имеет значение FALSE, необходимо вызвать расписание для запуска анимации в указанное время.  
  
##  <a name="applytransitions"></a>CAnimationGroup::ApplyTransitions  
 Применяет переходы для объектов анимации.  
  
```  
void ApplyTransitions();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод ПОДТВЕРЖДАЕТ в режиме отладки, если раскадровка не был создан. Его создает все переходы, во-первых, затем добавляет «static» опорных кадров (кадры, зависящие от смещения), добавляет переходы, которые не зависят от опорные кадры, добавляет опорные кадры, в зависимости от того, переходы и другие ключевые кадры и наконец добавляет переходы, которые зависят от опорные кадры.  
  
##  <a name="canimationgroup"></a>CAnimationGroup::CAnimationGroup  
 Создает группу анимации.  
  
```  
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentController`  
 Указатель на контроллер анимации, который создает группу.  
  
 `nGroupID`  
 Указывает GroupID.  
  
##  <a name="createtransitions"></a>CAnimationGroup::CreateTransitions  
 Вспомогательный класс, создающий объекты COM перехода.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 ИСТИНА, если метод выполнен успешно, в противном случае — значение FALSE.  
  
##  <a name="findanimationobject"></a>CAnimationGroup::FindAnimationObject  
 Выполняет поиск объекта анимации, содержащий переменную указанного анимации.  
  
```  
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Параметры  
 `pVariable`  
 Указатель на переменную анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель объекта анимации, или значение NULL, если анимация объект не найден.  
  
##  <a name="getgroupid"></a>CAnimationGroup::GetGroupID  
 Возвращает GroupID.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор группы.  
  
##  <a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions  
 Указывает, как очистить переходы из анимации объектов, принадлежащих группе. Если этот элемент имеет значение TRUE, переходы будут удалены автоматически запланированному анимации. В противном случае необходимо вручную удалить переходы.  
  
```  
BOOL m_bAutoclearTransitions;  
```  
  
##  <a name="m_bautodestroyanimationobjects"></a>CAnimationGroup::m_bAutodestroyAnimationObjects  
 Указывает, как для уничтожения объектов анимации. Если этот параметр имеет значение TRUE, объекты анимации будут уничтожены автоматически при удалении группы. В противном случае объекты анимации необходимо удалить вручную. Значение по умолчанию — FALSE. Это значение равно TRUE только в том случае, если все объекты анимации, которые принадлежат группе выделяется динамически с помощью оператора new.  
  
```  
BOOL m_bAutodestroyAnimationObjects;  
```  
  
##  <a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes  
 Указывает способ удаления ключевых кадров. Если это значение равно TRUE, все ключевые кадры удаляются и уничтожено; в противном случае они удаляются только из списка. Значение по умолчанию — TRUE.  
  
```  
BOOL m_bAutodestroyKeyframes;  
```  
  
##  <a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects  
 Содержит список объектов анимации.  
  
```  
CObList m_lstAnimationObjects;  
```  
  
##  <a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames  
 Содержит список ключевых кадров.  
  
```  
CObList m_lstKeyFrames;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID  
 Уникальный идентификатор группы анимации.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationGroup::m_pParentController  
 Указатель на контроллер анимации, к которой принадлежит эта группа.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard  
 Указывает раскадровки анимации. Этот указатель является действительным только после вызова на анимировать.  
  
```  
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;  
```  
  
##  <a name="removekeyframes"></a>CAnimationGroup::RemoveKeyframes  
 Удаляет и при необходимости уничтожает все ключевые кадры, которые принадлежат группе анимации.  
  
```  
void RemoveKeyframes();
```  
  
### <a name="remarks"></a>Примечания  
 Если член m_bAutodestroyKeyframes имеет значение TRUE, то ключевые кадры удаляются и уничтожения, в противном случае опорные кадры просто удаляются из внутреннего списка ключевых кадров.  
  
##  <a name="removetransitions"></a>CAnimationGroup::RemoveTransitions  
 Удаляет переходы из объекта анимации, которые принадлежат группе анимации.  
  
```  
void RemoveTransitions();
```  
  
### <a name="remarks"></a>Примечания  
 Если флаг m_bAutoclearTransitions имеет значение TRUE, этот метод обрабатывает в цикле всех объектов анимации, которые принадлежат к группе и вызывает CAnimationObject::ClearTransitions(FALSE).  
  
##  <a name="schedule"></a>CAnimationGroup::Schedule  
 Планирует анимации в указанное время.  
  
```  
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```  
  
### <a name="parameters"></a>Параметры  
 `pTimer`  
 Указатель таймера анимации.  
  
 `time`  
 Указывает время планирования анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; Значение FALSE при сбое метода или если анимация не был вызван с bScheduleNow значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для планирования анимации в указанное время. Необходимо вызвать анимировать с bScheduleNow равным FALSE.  
  
##  <a name="setautodestroytransitions"></a>CAnimationGroup::SetAutodestroyTransitions  
 Указывает, что переходы уничтожить всех объектов анимации, которые принадлежат группе автоматически.  
  
```  
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutoDestroy`  
 Указывает способ удаления переходов.  
  
### <a name="remarks"></a>Примечания  
 Это значение равно FALSE, только в том случае, если выделить переходы в стеке. Значение по умолчанию — TRUE, поэтому настоятельно рекомендуется для выделения объектов переход с помощью оператора new.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

