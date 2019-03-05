---
title: Класс CBaseTransition
ms.date: 11/04/2016
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
ms.openlocfilehash: 1f9bc3708974511506741a35c11676df2b0be592
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258376"
---
# <a name="cbasetransition-class"></a>Класс CBaseTransition

Представляет базовый переход.

## <a name="syntax"></a>Синтаксис

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-enumerations"></a>Открытые перечисления

|Имя|Описание|
|----------|-----------------|
|[Перечисление CBaseTransition::TRANSITION_TYPE](#transition_type_enumeration)|Определяет типы перехода, в настоящее время поддерживает реализацию MFC Windows API анимации.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBaseTransition::CBaseTransition](#cbasetransition)|Создает объект базового перехода.|
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Деструктор Вызывается при уничтожении объекта перехода.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Добавляет переход к раскадровке.|
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Добавляет переход к раскадровке.|
|[CBaseTransition::Clear](#clear)|Выпуски инкапсулированы IUIAnimationTransition COM-объекта.|
|[CBaseTransition::Create](#create)|Создает COM переход.|
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Возвращает начала опорного кадра.|
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Возвращает указатель на связанных переменной.|
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Возвращает начала опорного кадра.|
|[CBaseTransition::GetTransition](#gettransition)|Перегружен. Возвращает указатель на базовый объект COM перехода.|
|[CBaseTransition::GetType](#gettype)|Возвращает типа перехода.|
|[CBaseTransition::IsAdded](#isadded)|Указывает, добавлен ли переход к раскадровке.|
|[CBaseTransition::SetKeyframes](#setkeyframes)|Задает опорные кадры для перехода.|
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Устанавливает связь между переменной анимации и перехода.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CBaseTransition::m_bAdded](#m_badded)|Указывает, добавлен ли переход к раскадровке.|
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Хранит указатель указывает окончание перехода опорный кадр.|
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|Указатель на переменную анимации, который анимируется с переходом, хранящиеся в m_transition.|
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Содержит указатель на начало перехода опорный кадр.|
|[CBaseTransition::m_transition](#m_transition)|Содержит указатель на IUIAnimationTransition. Значение NULL, если COM-объект перехода не был создан.|
|[CBaseTransition::m_type](#m_type)|Сохраняет тип перехода.|

## <a name="remarks"></a>Примечания

Этот класс инкапсулирует интерфейс IUIAnimationTransition и служит базовым классом для всех переходов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="_dtorcbasetransition"></a>  CBaseTransition:: ~ CBaseTransition

Деструктор Вызывается при уничтожении объекта перехода.

```
virtual ~CBaseTransition();
```

##  <a name="addtostoryboard"></a>  CBaseTransition::AddToStoryboard

Добавляет переход к раскадровке.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровки, который анимируется связанных переменной.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход был успешно добавлен к раскадровке.

### <a name="remarks"></a>Примечания

Относится переход к соответствующим переменной в раскадровке. Если это первый переход к этой переменной в этой раскадровке, переход начинается в начале раскадровки. В противном случае переход добавляется перехода, наиболее недавно добавлена в переменную.

##  <a name="addtostoryboardatkeyframes"></a>  CBaseTransition::AddToStoryboardAtKeyframes

Добавляет переход к раскадровке.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровки, который анимируется связанных переменной.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход был успешно добавлен к раскадровке.

### <a name="remarks"></a>Примечания

Относится переход к соответствующим переменной в раскадровке. Если был задан опорный кадр start, переход начинается с этого опорного кадра. Если указан конечный опорный кадр, переход начинается с начала опорный кадр и останавливается на окончания опорного кадра. Если переход был создан с параметром длительность указано, это время перезаписывается время между опорными кадрами начала и окончания. Если было указано без опорного кадра, переход добавляется перехода, наиболее недавно добавлена в переменную.

##  <a name="cbasetransition"></a>  CBaseTransition::CBaseTransition

Создает объект базового перехода.

```
CBaseTransition();
```

##  <a name="clear"></a>  CBaseTransition::Clear

Выпуски инкапсулированы IUIAnimationTransition COM-объекта.

```
void Clear();
```

### <a name="remarks"></a>Примечания

Этот метод должен вызываться из производного класса метода Create во избежание утечки IUITransition интерфейс.

##  <a name="create"></a>  CBaseTransition::Create

Создает COM переход.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая создает стандартные переходов. Он может иметь значение NULL для пользовательских переходов.

*pFactory*<br/>
Указатель на фабрику перехода, которая создает пользовательские переходы. Он может иметь значение NULL для стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход COM-объект был успешно создан; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Это чистой виртуальной функции, которое должно быть переопределено в производном классе. Он вызывается платформой для создания базового COM-объект перехода.

##  <a name="getendkeyframe"></a>  CBaseTransition::GetEndKeyframe

Возвращает начала опорного кадра.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель опорного кадра, или значение NULL, если не нужно включать переход между опорными кадрами.

### <a name="remarks"></a>Примечания

Этот метод может использоваться для доступа к объект опорный кадр, который был ранее установлен с SetKeyframes. Она вызвана кода верхнего уровня, при добавлении переходы на раскадровку.

##  <a name="getrelatedvariable"></a>  CBaseTransition::GetRelatedVariable

Возвращает указатель на связанных переменной.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на переменную анимации или значение NULL, если переменной анимации не задал SetRelatedVariable.

### <a name="remarks"></a>Примечания

Это метод доступа к переменной связанных анимации.

##  <a name="getstartkeyframe"></a>  CBaseTransition::GetStartKeyframe

Возвращает начала опорного кадра.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель опорного кадра, или значение NULL, если переход не должен запускаться после опорного кадра.

### <a name="remarks"></a>Примечания

Этот метод может использоваться для доступа к объект опорный кадр, который был ранее установлен с SetKeyframes. Она вызвана кода верхнего уровня, при добавлении переходы на раскадровку.

##  <a name="gettransition"></a>  CBaseTransition::GetTransition

Возвращает указатель на базовый объект COM перехода.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая создает стандартные переходов. Он может иметь значение NULL для пользовательских переходов.

*pFactory*<br/>
Указатель на фабрику перехода, которая создает пользовательские переходы. Он может иметь значение NULL для стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Не удалось создать допустимый указатель IUIAnimationTransition или значение NULL, если базовый переход.

### <a name="remarks"></a>Примечания

Этот метод возвращает указатель на базовый объект COM перехода и при необходимости создает его.

##  <a name="gettype"></a>  CBaseTransition::GetType

Возвращает типа перехода.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Один из TRANSITION_TYPE значений перечисления.

### <a name="remarks"></a>Примечания

Этот метод может использоваться для идентификации объекта перехода по его типу. Тип задается в конструкторе производного класса.

##  <a name="isadded"></a>  CBaseTransition::IsAdded

Указывает, добавлен ли переход к раскадровке.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если переход был добавлен к раскадровке, в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот флаг установлен внутренне при верхнего уровня код добавляет переходы на раскадровку.

##  <a name="m_badded"></a>  CBaseTransition::m_bAdded

Указывает, добавлен ли переход к раскадровке.

```
BOOL m_bAdded;
```

##  <a name="m_pendkeyframe"></a>  CBaseTransition::m_pEndKeyframe

Хранит указатель указывает окончание перехода опорный кадр.

```
CBaseKeyFrame* m_pEndKeyframe;
```

##  <a name="m_prelatedvariable"></a>  CBaseTransition::m_pRelatedVariable

Указатель на переменную анимации, который анимируется с переходом, хранящиеся в m_transition.

```
CAnimationVariable* m_pRelatedVariable;
```

##  <a name="m_pstartkeyframe"></a>  CBaseTransition::m_pStartKeyframe

Содержит указатель на начало перехода опорный кадр.

```
CBaseKeyFrame* m_pStartKeyframe;
```

##  <a name="m_transition"></a>  CBaseTransition::m_transition

Содержит указатель на IUIAnimationTransition. Значение NULL, если COM-объект перехода не был создан.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

##  <a name="m_type"></a>  CBaseTransition::m_type

Сохраняет тип перехода.

```
TRANSITION_TYPE m_type;
```

##  <a name="setkeyframes"></a>  CBaseTransition::SetKeyframes

Задает опорные кадры для перехода.

```
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Параметры

*pStart*<br/>
Опорный кадр, который задает начало перехода.

*Отложить*<br/>
Опорный кадр, который указывает конец перехода.

### <a name="remarks"></a>Примечания

Этот метод указывает перехода для запуска после указанного опорного кадра и, при необходимости, если ожидаемый не равно NULL, в конце до указанного опорного кадра. Если переход был создан с параметром длительность указано, это время перезаписывается время между опорными кадрами начала и окончания.

##  <a name="setrelatedvariable"></a>  CBaseTransition::SetRelatedVariable

Устанавливает связь между переменной анимации и перехода.

```
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Параметры

*pVariable*<br/>
Указатель на переменную связанных анимации.

### <a name="remarks"></a>Примечания

Устанавливает связь между переменной анимации и перехода. Переход может применяться только к одной переменной.

##  <a name="transition_type_enumeration"></a>  Перечисление CBaseTransition::TRANSITION_TYPE

Определяет типы перехода, в настоящее время поддерживает реализацию MFC Windows API анимации.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Примечания

Тип перехода задается в конструкторе класса определенного перехода. Например CSinusoidalTransitionFromRange задает SINUSOIDAL_FROM_RANGE его тип.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
