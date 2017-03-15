---
title: "Класс CAnimationColor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- afxanimationcontroller/CAnimationColor
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor class
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: e053986737b8e62103666787b99b01cbf19cdc60
ms.lasthandoff: 02/24/2017

---
# <a name="canimationcolor-class"></a>Класс CAnimationColor
Реализует функции цвета, красный, зеленый и синий компоненты которого могут быть анимированы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|Перегружен. Создает объект анимации цвета.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|Добавление переходов для красного, зеленого и синего компонентов.|  
|[CAnimationColor::GetB](#getb)|Предоставляет доступ к CAnimationVariable, представляющий синего компонента.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для компонентов цвета.|  
|[CAnimationColor::GetG](#getg)|Предоставляет доступ к CAnimationVariable, представляющий зеленого компонента.|  
|[CAnimationColor::GetR](#getr)|Предоставляет доступ к CAnimationVariable, представляющий красного компонента.|  
|[CAnimationColor::GetValue](#getvalue)|Возвращает текущее значение.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|Назначает цвет CAnimationColor.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|Инкапсулированный анимации переменной, представляющей синего компонента цвета анимации.|  
|[CAnimationColor::m_gValue](#m_gvalue)|Инкапсулированный анимации переменной, представляющей зеленого компонента цвета анимации.|  
|[CAnimationColor::m_rValue](#m_rvalue)|Инкапсулированный анимации переменной, представляющей красного компонента цвета анимации.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationColor инкапсулирует трех объектов CAnimationVariable и представляют в приложениях цвет. Например, этот класс можно использовать для анимации цвета любого объекта на экране (например цвет текста и т. д цвет фона). Чтобы использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода, применяемый для красного, зеленого и синего компонентов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtransitiona--canimationcoloraddtransition"></a><a name="addtransition"></a>CAnimationColor::AddTransition  
 Добавление переходов для красного, зеленого и синего компонентов.  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pRTransition`  
 Переход для красного компонента.  
  
 `pGTransition`  
 Переход для зеленого компонента.  
  
 `pBTransition`  
 Переход для синего компонента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для Добавление указанного переходов во внутренний список переходов для применения к анимации переменные, представляющие цветовых компонентов. При добавлении переходов, они не применяются сразу и хранятся в внутренний список. Переходы применяются (Добавление в раскадровку для определенного значения) при вызове CAnimationController::AnimateGroup. Если не требуется применить переход к одному из компонентов цвета, можно передать значение NULL.  
  
##  <a name="a-namecanimationcolora--canimationcolorcanimationcolor"></a><a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 Создает объект CAnimationColor.  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Задает цвета по умолчанию.  
  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `nObjectID`  
 Указывает идентификатор объекта.  
  
 `dwUserData`  
 Задает определяемые пользователем данные.  
  
### <a name="remarks"></a>Примечания  
 Объект создан со значениями по умолчанию красный, зеленый, синий, идентификатор объекта и идентификатор группы, которая будет иметь значение 0. Они могут быть изменены во время выполнения с помощью SetDefaultValue и SetID.  
  
##  <a name="a-namegetanimationvariablelista--canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 Помещает инкапсулированный анимации переменные в список.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Параметры  
 `lst`  
 Когда функция возвращает значение, он содержит указатели на три CAnimationVariable объекты, представляющие красного, зеленого и синего компонентов.  
  
##  <a name="a-namegetba--canimationcolorgetb"></a><a name="getb"></a>CAnimationColor::GetB  
 Предоставляет доступ к CAnimationVariable, представляющий синего компонента.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий синего компонента.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий синего компонента.  
  
##  <a name="a-namegetdefaultvaluea--canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 Возвращает значения по умолчанию для компонентов цвета.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 COLORREF значение, содержащее значения по умолчанию для компонентов RGB.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения значения по умолчанию, которой было установлено ранее, конструктор или SetDefaultValue.  
  
##  <a name="a-namegetga--canimationcolorgetg"></a><a name="getg"></a>CAnimationColor::GetG  
 Предоставляет доступ к CAnimationVariable, представляющий зеленого компонента.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылки на компонент представления зеленый инкапсулированный CAnimationVariable.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к указанному компоненту зеленый CAnimationVariable для представления.  
  
##  <a name="a-namegetra--canimationcolorgetr"></a><a name="getr"></a>CAnimationColor::GetR  
 Предоставляет доступ к CAnimationVariable, представляющий красного компонента.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий красного компонента.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий красного компонента.  
  
##  <a name="a-namegetvaluea--canimationcolorgetvalue"></a><a name="getvalue"></a>CAnimationColor::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Выходные данные. Содержит текущее значение при возвращении данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение были успешно извлечены; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения анимации цвета. Если этот метод не или базовые объекты COM для цветовых компонентов не был инициализирован, цвет содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.  
  
##  <a name="a-namembvaluea--canimationcolormbvalue"></a><a name="m_bvalue"></a>CAnimationColor::m_bValue  
 Инкапсулированный анимации переменной, представляющей синего компонента цвета анимации.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="a-namemgvaluea--canimationcolormgvalue"></a><a name="m_gvalue"></a>CAnimationColor::m_gValue  
 Инкапсулированный анимации переменной, представляющей зеленого компонента цвета анимации.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="a-namemrvaluea--canimationcolormrvalue"></a><a name="m_rvalue"></a>CAnimationColor::m_rValue  
 Инкапсулированный анимации переменной, представляющей красного компонента цвета анимации.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="a-nameoperatorcolorrefa--canimationcoloroperator-colorref"></a><a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatoreqa--canimationcoloroperator"></a><a name="operator_eq"></a>CAnimationColor::operator =  
 Назначает цвет CAnimationColor.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Указывает новое значение анимации цвета.  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, который воссоздает базовых объектов COM для компонентов цвета, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
##  <a name="a-namesetdefaultvaluea--canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Указывает новые значения по умолчанию для красного, зеленого и синего компонентов.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для задания значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию цветовых компонентов анимации цвета. Также воссоздает базовых объектов COM, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

