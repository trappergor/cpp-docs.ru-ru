---
title: "Класс CBaseTransition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
dev_langs:
- C++
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a925de05d301d213d67bb699af47d0453478ffc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cbasetransition-class"></a>Класс CBaseTransition
Представляет базовый переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-enumerations"></a>Открытые перечисления  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Перечисление CBaseTransition::TRANSITION_TYPE](#transition_type_enumeration)|Определяет типы перехода, в настоящее время поддерживается реализации MFC Windows API анимации.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|Создает объект базового перехода.|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Деструктор Вызывается при уничтожении объекта перехода.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Добавляет переход раскадровки.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Добавляет переход раскадровки.|  
|[CBaseTransition::Clear](#clear)|Выпуски инкапсулированы IUIAnimationTransition COM-объекта.|  
|[CBaseTransition::Create](#create)|Создает COM переход.|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Возвращает запустите опорного кадра.|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Возвращает указатель на связанные переменной.|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Возвращает запустите опорного кадра.|  
|[CBaseTransition::GetTransition](#gettransition)|Перегружен. Возвращает указатель базового COM-объекта перехода.|  
|[CBaseTransition::GetType](#gettype)|Возвращает типа перехода.|  
|[CBaseTransition::IsAdded](#isadded)|Указывает, были ли добавлены переход раскадровки.|  
|[CBaseTransition::SetKeyframes](#setkeyframes)|Задает опорные кадры для перехода.|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Устанавливает связь между переменной анимации и перехода.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|Указывает, были ли добавлены переход раскадровки.|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Хранит указатель на ключевой кадр, который указывает конец перехода.|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|Указатель на переменную анимации, что анимации с переходом, хранящиеся в m_transition.|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Хранит указатель на ключевой кадр, задающее начало перехода.|  
|[CBaseTransition::m_transition](#m_transition)|Содержит указатель на IUIAnimationTransition. Значение NULL, если не был создан переход COM-объектом.|  
|[CBaseTransition::m_type](#m_type)|Сохраняет тип перехода.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс инкапсулирует интерфейс IUIAnimationTransition и служит базовым классом для всех переходов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="_dtorcbasetransition"></a>CBaseTransition:: ~ CBaseTransition  
 Деструктор Вызывается при уничтожении объекта перехода.  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard  
 Добавляет переход раскадровки.  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на раскадровку, которой будет анимировать связанные переменной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход был успешно добавлен раскадровки.  
  
### <a name="remarks"></a>Примечания  
 Применяет перехода на связанные переменную в раскадровку. Если это первый переход, применить к этой переменной в этой раскадровке перехода начинается с начала раскадровки. В противном случае переход добавляется переход, недавно добавляется в переменную.  
  
##  <a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 Добавляет переход раскадровки.  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на раскадровку, которой будет анимировать связанные переменной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход был успешно добавлен раскадровки.  
  
### <a name="remarks"></a>Примечания  
 Применяет перехода на связанные переменную в раскадровку. Если указан ключевой кадр start, переход начинается с этого ключевого кадра. Если указан ключевой кадр end, переход начинается с начала ключевой кадр и и останавливается из-за окончания опорного кадра. Если переход был создан с параметром длительность указано, длительности перезаписывается время между ключевыми кадрами начала и окончания. Если было указано без ключевого кадра, переход добавляется переход, недавно добавляется в переменную.  
  
##  <a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 Создает объект базового перехода.  
  
```  
CBaseTransition();
```  
  
##  <a name="clear"></a>CBaseTransition::Clear  
 Выпуски инкапсулированы IUIAnimationTransition COM-объекта.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод следует вызывать из производного класса метода Create во избежание утечки IUITransition интерфейса.  
  
##  <a name="create"></a>CBaseTransition::Create  
 Создает COM переход.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pLibrary`  
 Указатель на переход библиотеку, которая создает стандартный переходов. Он может быть NULL для пользовательских переходов.  
  
 `pFactory`  
 Указатель на переход фабрики, создающий пользовательский переходов. Он может быть NULL для стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход COM-объект был успешно создан; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Это чистой виртуальной функции, который должен быть переопределен в производном классе. Он вызывается платформой для создания базового COM-объекта перехода.  
  
##  <a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 Возвращает запустите опорного кадра.  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель опорный кадр, или значение NULL, если не нужно вставить переход между ключевыми кадрами.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для доступа к объекту опорный кадр, который SetKeyframes было установлено ранее. Он вызывается кода верхнего уровня, при добавлении переходы на раскадровку.  
  
##  <a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable  
 Возвращает указатель на связанные переменной.  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель переменной анимации, или значение NULL, если не был задан SetRelatedVariable переменной анимации.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа для переменной связанные анимации.  
  
##  <a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 Возвращает запустите опорного кадра.  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель опорный кадр, или значение NULL, если переход не должен запускаться после ключевого кадра.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для доступа к объекту опорный кадр, который SetKeyframes было установлено ранее. Он вызывается кода верхнего уровня, при добавлении переходы на раскадровку.  
  
##  <a name="gettransition"></a>CBaseTransition::GetTransition  
 Возвращает указатель базового COM-объекта перехода.  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>Параметры  
 `pLibrary`  
 Указатель на переход библиотеку, которая создает стандартный переходов. Он может быть NULL для пользовательских переходов.  
  
 `pFactory`  
 Указатель на переход фабрики, создающий пользовательский переходов. Он может быть NULL для стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Не удается создать допустимый указатель на IUIAnimationTransition или значение NULL, если базовый переход.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает указатель на базовый объект COM перехода и при необходимости создает его.  
  
##  <a name="gettype"></a>CBaseTransition::GetType  
 Возвращает типа перехода.  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из TRANSITION_TYPE значений перечисления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для идентификации объекта перехода по его типу. Тип задается в конструкторе в производном классе.  
  
##  <a name="isadded"></a>CBaseTransition::IsAdded  
 Указывает, были ли добавлены переход раскадровки.  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если переход был добавлен раскадровки, в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг устанавливается внутри верхнего уровня код добавляет переходы на раскадровку.  
  
##  <a name="m_badded"></a>CBaseTransition::m_bAdded  
 Указывает, были ли добавлены переход раскадровки.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 Хранит указатель на ключевой кадр, который указывает конец перехода.  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 Указатель на переменную анимации, что анимации с переходом, хранящиеся в m_transition.  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 Хранит указатель на ключевой кадр, задающее начало перехода.  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="m_transition"></a>CBaseTransition::m_transition  
 Содержит указатель на IUIAnimationTransition. Значение NULL, если не был создан переход COM-объектом.  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="m_type"></a>CBaseTransition::m_type  
 Сохраняет тип перехода.  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="setkeyframes"></a>CBaseTransition::SetKeyframes  
 Задает опорные кадры для перехода.  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pStart`  
 Ключевой кадр, который задает начало перехода.  
  
 `pEnd`  
 Ключевой кадр, который указывает конец перехода.  
  
### <a name="remarks"></a>Примечания  
 Этот метод указывает переход для запуска после указанного ключевого кадра и при необходимости отложите не равно NULL, завершить до указанного ключевого кадра. Если переход был создан с параметром длительность указано, длительности перезаписывается время между ключевыми кадрами начала и окончания.  
  
##  <a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 Устанавливает связь между переменной анимации и перехода.  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Параметры  
 `pVariable`  
 Указатель на переменную связанные анимации.  
  
### <a name="remarks"></a>Примечания  
 Устанавливает связь между переменной анимации и перехода. Переход может применяться только к одной переменной.  
  
##  <a name="transition_type_enumeration"></a>Перечисление CBaseTransition::TRANSITION_TYPE  
 Определяет типы перехода, в настоящее время поддерживается реализации MFC Windows API анимации.  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип перехода задается в конструкторе отдельный переход. Например CSinusoidalTransitionFromRange задает SINUSOIDAL_FROM_RANGE его тип.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
