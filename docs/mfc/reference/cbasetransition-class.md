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
- CBaseTransition class
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b979d03587ada42486d0462733dfe6fd22f9f7cc
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetransition-class"></a>Класс CBaseTransition
Представляет базовый переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-enumerations"></a>Открытые перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление CBaseTransition::TRANSITION_TYPE](#transition_type_enumeration)|Определяет типы перехода, в настоящее время поддерживается реализация API анимации Windows в MFC.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|Создает объект базового перехода.|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Деструктор Вызывается при уничтожении объекта перехода.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Добавляет перехода в раскадровку.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Добавляет перехода в раскадровку.|  
|[CBaseTransition::Clear](#clear)|Выпуски инкапсуляцию IUIAnimationTransition COM-объект.|  
|[CBaseTransition::Create](#create)|Создает COM переход.|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Возвращает начала опорного кадра.|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Возвращает указатель на связанные переменной.|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Возвращает начала опорного кадра.|  
|[CBaseTransition::GetTransition](#gettransition)|Перегружен. Возвращает указатель базового COM-объекта перехода.|  
|[CBaseTransition::GetType](#gettype)|Возвращает переход типа.|  
|[CBaseTransition::IsAdded](#isadded)|Указывает, были ли добавлены перехода в раскадровку.|  
|[CBaseTransition::SetKeyframes](#setkeyframes)|Задает опорные кадры для перехода.|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Устанавливает связь между переменной анимации и перехода.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|Указывает, были ли добавлены перехода в раскадровку.|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Хранит указатель опорного кадра, который указывает конец перехода.|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|Указатель на переменную анимации, который анимируется с переходом, хранящиеся в m_transition.|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Хранит указатель опорного кадра, который указывает начало перехода.|  
|[CBaseTransition::m_transition](#m_transition)|Хранит указатель на IUIAnimationTransition. Значение NULL, если переход COM-объект не был создан.|  
|[CBaseTransition::m_type](#m_type)|Хранит тип перехода.|  
  
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
 Добавляет перехода в раскадровку.  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на раскадровки, который анимируется связанной переменной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход был успешно добавлен в раскадровку.  
  
### <a name="remarks"></a>Примечания  
 Относится к связанной переменной в раскадровке перехода. Если это первый переход, применяется к этой переменной в этой раскадровке перехода начинается в начале раскадровки. В противном случае — переход добавляется переход, наиболее часто добавляется в переменную.  
  
##  <a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 Добавляет перехода в раскадровку.  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на раскадровки, который анимируется связанной переменной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход был успешно добавлен в раскадровку.  
  
### <a name="remarks"></a>Примечания  
 Относится к связанной переменной в раскадровке перехода. Если был задан опорный кадр start, переход начинается, опорный кадр. Если указан окончания опорного кадра, перехода начинается с начала опорный кадр и и останавливается на окончания опорного кадра. Если переход был создан с параметром длительность указано, длительности заменяются промежуток времени между опорными кадрами начала и окончания. Если кадр не была указана, переход добавляется переход, наиболее часто добавляется в переменную.  
  
##  <a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 Создает объект базового перехода.  
  
```  
CBaseTransition();
```  
  
##  <a name="clear"></a>CBaseTransition::Clear  
 Выпуски инкапсуляцию IUIAnimationTransition COM-объект.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться из метода Create в производном классе, во избежание утечки интерфейс IUITransition.  
  
##  <a name="create"></a>CBaseTransition::Create  
 Создает COM переход.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pLibrary`  
 Указатель на переход библиотеки, которая создает стандартные переходов. Он может иметь значение NULL для пользовательских переходов.  
  
 `pFactory`  
 Указатель на переход фабрики, создающий пользовательский переходов. Он может иметь значение NULL для стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход COM-объект был успешно создан; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Это чисто виртуальную функцию, который должен быть переопределен в производном классе. Он вызывается платформой для создания базового COM-объект перехода.  
  
##  <a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 Возвращает начала опорного кадра.  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель опорного кадра, или значение NULL, если не нужно включать переход между опорными кадрами.  
  
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
 Это метод доступа для переменной связанных анимации.  
  
##  <a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 Возвращает начала опорного кадра.  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель опорного кадра, или значение NULL, если переход не должен запускаться после опорного кадра.  
  
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
 Указатель на переход библиотеки, которая создает стандартные переходов. Он может иметь значение NULL для пользовательских переходов.  
  
 `pFactory`  
 Указатель на переход фабрики, создающий пользовательский переходов. Он может иметь значение NULL для стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Не удается создать допустимый указатель на IUIAnimationTransition или значение NULL, если базовый переход.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает указатель на базовый объект COM перехода и при необходимости создает его.  
  
##  <a name="gettype"></a>CBaseTransition::GetType  
 Возвращает переход типа.  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из TRANSITION_TYPE значений перечисления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может использоваться для идентификации объекта перехода по его типу. Тип задается в конструкторе производного класса.  
  
##  <a name="isadded"></a>CBaseTransition::IsAdded  
 Указывает, были ли добавлены перехода в раскадровку.  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если переход были добавлены раскадровки, в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг установлен внутри кода верхнего уровня добавляет переходы на раскадровку.  
  
##  <a name="m_badded"></a>CBaseTransition::m_bAdded  
 Указывает, были ли добавлены перехода в раскадровку.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 Хранит указатель опорного кадра, который указывает конец перехода.  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 Указатель на переменную анимации, который анимируется с переходом, хранящиеся в m_transition.  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 Хранит указатель опорного кадра, который указывает начало перехода.  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="m_transition"></a>CBaseTransition::m_transition  
 Хранит указатель на IUIAnimationTransition. Значение NULL, если переход COM-объект не был создан.  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="m_type"></a>CBaseTransition::m_type  
 Хранит тип перехода.  
  
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
 Ключевой кадр, который указывает начало перехода.  
  
 `pEnd`  
 Ключевой кадр, который указывает конец перехода.  
  
### <a name="remarks"></a>Примечания  
 Этот метод указывает переход для запуска после указанного опорного кадра и при необходимости не равно NULL, ожидать завершения до указанного опорного кадра. Если переход был создан с параметром длительность указано, длительности заменяются промежуток времени между опорными кадрами начала и окончания.  
  
##  <a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 Устанавливает связь между переменной анимации и перехода.  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Параметры  
 `pVariable`  
 Указатель на переменную связанных анимации.  
  
### <a name="remarks"></a>Примечания  
 Устанавливает связь между переменной анимации и перехода. Переход может применяться только к одной переменной.  
  
##  <a name="transition_type_enumeration"></a>Перечисление CBaseTransition::TRANSITION_TYPE  
 Определяет типы перехода, в настоящее время поддерживается реализация API анимации Windows в MFC.  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип перехода задается в конструкторе определенного перехода. Например CSinusoidalTransitionFromRange задает SINUSOIDAL_FROM_RANGE его тип.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

