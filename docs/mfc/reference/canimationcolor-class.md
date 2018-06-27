---
title: Класс CAnimationColor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 462882957999d607809e80908ae4a25c628f18d4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951747"
---
# <a name="canimationcolor-class"></a>Класс CAnimationColor
Реализует функции цвета, красный, зеленый и синий компоненты которого могут быть анимированы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|Перегружен. Создает объект цветовой анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|Добавляет переходы для красного, зеленого и синего компонентов.|  
|[CAnimationColor::GetB](#getb)|Предоставляет доступ к CAnimationVariable, представляющий синего компонента.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для компонентов цвета.|  
|[CAnimationColor::GetG](#getg)|Предоставляет доступ к CAnimationVariable, представляющий зеленого компонента.|  
|[CAnimationColor::GetR](#getr)|Предоставляет доступ к CAnimationVariable, представляющий красного компонента.|  
|[CAnimationColor::GetValue](#getvalue)|Возвращает текущее значение.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|Назначает цвет CAnimationColor.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|Инкапсулированный анимации переменной, представляющей синего компонента цвета анимации.|  
|[CAnimationColor::m_gValue](#m_gvalue)|Инкапсулированный анимации переменной, представляющей зеленого компонента цвета анимации.|  
|[CAnimationColor::m_rValue](#m_rvalue)|Инкапсулированный анимации переменной, представляющей красного компонента цвета анимации.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationColor инкапсулирует трех объектов CAnimationVariable и представляют в приложениях цвет. Например, этот класс можно использовать для анимации цвета любого объекта на экране (как и цвет текста, фоновый цвет и т. д). Использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода, применяемый для красного, зеленого и синего компонентов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationColor::AddTransition  
 Добавляет переходы для красного, зеленого и синего компонентов.  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>Параметры  
 *pRTransition*  
 Переход для красного компонента.  
  
 *pGTransition*  
 Переход для зеленого компонента.  
  
 *pBTransition*  
 Переход для синего компонента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для добавления указанного переходов во внутренний список переходов для применения к анимации переменные, представляющие компонентов цвета. При добавлении переходов, они не, в силу немедленно и сохраняются во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup. Если не нужно применять переход к одному из компонентов цвета, можно передать значение NULL.  
  
##  <a name="canimationcolor"></a>  CAnimationColor::CAnimationColor  
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
 *Цвет*  
 Задает цвета по умолчанию.  
  
 *nGroupID*  
 Указывает идентификатор группы.  
  
 *nObjectID*  
 Указывает идентификатор объекта.  
  
 *dwUserData*  
 Задает определяемые пользователем данные.  
  
### <a name="remarks"></a>Примечания  
 Объект создается со значениями по умолчанию для красный, зеленый, синий, идентификатор объекта и идентификатор группы, которому будет задано значение 0. Они могут быть изменены во время выполнения с помощью SetDefaultValue и SetID.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationColor::GetAnimationVariableList  
 Помещает инкапсулированный анимации переменные в список.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Параметры  
 *lst*  
 Когда функция возвращает значение, он содержит указатели на три CAnimationVariable объекты, представляющие красного, зеленого и синего компонентов.  
  
##  <a name="getb"></a>  CAnimationColor::GetB  
 Предоставляет доступ к CAnimationVariable, представляющий синего компонента.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий синего компонента.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий синего компонента.  
  
##  <a name="getdefaultvalue"></a>  CAnimationColor::GetDefaultValue  
 Возвращает значения по умолчанию для компонентов цвета.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 COLORREF значение, содержащее значения по умолчанию для компонентов RGB.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения по умолчанию значение, которое было установлено ранее, конструктор или SetDefaultValue.  
  
##  <a name="getg"></a>  CAnimationColor::GetG  
 Предоставляет доступ к CAnimationVariable, представляющий зеленого компонента.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на компонент представляющих зеленый инкапсулированный CAnimationVariable.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к указанному компоненту зеленый CAnimationVariable для представления.  
  
##  <a name="getr"></a>  CAnimationColor::GetR  
 Предоставляет доступ к CAnimationVariable, представляющий красного компонента.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий красного компонента.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий красного компонента.  
  
##  <a name="getvalue"></a>  CAnimationColor::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет*  
 Выходные данные. При возвращении этим методом, содержит текущее значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение было успешно извлечено; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения цвета анимации. Если этот метод завершается ошибкой, или базового COM-объектов для компонентов цвета не был инициализирован, цвет содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.  
  
##  <a name="m_bvalue"></a>  CAnimationColor::m_bValue  
 Инкапсулированный анимации переменной, представляющей синего компонента цвета анимации.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>  CAnimationColor::m_gValue  
 Инкапсулированный анимации переменной, представляющей зеленого компонента цвета анимации.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>  CAnimationColor::m_rValue  
 Инкапсулированный анимации переменной, представляющей красного компонента цвета анимации.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>  CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="operator_eq"></a>  CAnimationColor::operator =  
 Назначает цвет CAnimationColor.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет*  
 Указывает новое значение цвета анимации.  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, который повторно создает базовые объекты COM для компонентов цвета, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо повторно включить эти события.  
  
##  <a name="setdefaultvalue"></a>  CAnimationColor::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет*  
 Указывает новые значения по умолчанию для красного, зеленого и синего компонентов.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для задания значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию цвет компонентов цвета анимации. Также воссоздает базовые COM-объекты, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо повторно включить эти события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
