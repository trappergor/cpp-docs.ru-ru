---
title: "Класс CAnimationValue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
dev_langs: C++
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b37801619fae84519dde000c922d34c4b9e1509
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="canimationvalue-class"></a>Класс CAnimationValue
Реализует функции объекта анимации, имеющего одно значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](#canimationvalue)|Перегружен. Создает объект CAnimationValue.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](#addtransition)|Добавляет переход, применяемый к значению.|  
|[CAnimationValue::GetValue](#getvalue)|Перегружен. Возвращает текущее значение.|  
|[CAnimationValue::GetVariable](#getvariable)|Предоставляет доступ к переменной инкапсулированный анимации.|  
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Помещает переменную инкапсулированный анимации в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationValue::operator DOUBLE](#operator_double)|Обеспечивает преобразование между CAnimationValue и DOUBLE.|  
|[CAnimationValue::operator INT32](#operator_int32)|Обеспечивает преобразование между CAnimationValue и INT32.|  
|[CAnimationValue::operator =](#operator_eq)|Перегружен. Присваивает значение типа INT32 CAnimationValue.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CAnimationValue::m_value](#m_value)|Инкапсулированный анимации переменной, представляющей значение анимации.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationValue инкапсулирует один объект CAnimationVariable и может представлять в приложениях одного анимированные значения. Например, этот класс можно использовать для анимированного прозрачность (эффект исчезания) угол (для поворота объектов), или для всех остальных случаях для создания анимации в зависимости от одного анимированные значения. Использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода, применяемый к значению.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationValue`
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationValue::AddTransition  
 Добавляет переход, применяемый к значению.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pTransition`  
 Указатель на объект перехода.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы добавить переход внутренний список переходов для применения к переменной анимации. При добавлении переходов, они не, в силу немедленно и сохраняются во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup.  
  
##  <a name="canimationvalue"></a>CAnimationValue::CAnimationValue  
 Создает объект CAnimationValue.  
  
```  
CAnimationValue();

 
CAnimationValue(
    DOUBLE dblDefaultValue,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dblDefaultValue`  
 Указывает значение по умолчанию.  
  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `nObjectID`  
 Указывает идентификатор объекта.  
  
 `dwUserData`  
 Задает определяемые пользователем данные.  
  
### <a name="remarks"></a>Примечания  
 Создает объект CAnimationValue со свойствами по умолчанию: значение по умолчанию, идентификатор группы и идентификатор объекта имеют значение 0.  
  
##  <a name="getanimationvariablelist"></a>CAnimationValue::GetAnimationVariableList  
 Помещает переменную инкапсулированный анимации в список.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Параметры  
 `lst`  
 Когда функция возвращает значение, он содержит указатель CAnimationVariable, представляющий анимированное значение.  
  
##  <a name="getvalue"></a>CAnimationValue::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(DOUBLE& dblValue);  
BOOL GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Параметры  
 `dblValue`  
 Выходные данные. Если функция возвращает он содержит текущее значение переменной анимации.  
  
 `nValue`  
 Выходные данные. Если функция возвращает он содержит текущее значение переменной анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение получены успешно. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения. Эта реализация вызывает инкапсулированный объект COM, и если вызов завершается ошибкой, этот метод возвращает значение по умолчанию, указанного ранее в конструкторе или с SetDefaultValue.  
  
##  <a name="getvariable"></a>CAnimationValue::GetVariable  
 Предоставляет доступ к переменной инкапсулированный анимации.  
  
```  
CAnimationVariable& GetVariable();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на переменную инкапсулированный анимации.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для доступа к переменной инкапсулированный анимации. Из CAnimationVariable получить доступ к основной объект IUIAnimationVariable, указатель может иметь значение NULL, если не был создан переменной анимации.  
  
##  <a name="m_value"></a>CAnimationValue::m_value  
 Инкапсулированный анимации переменной, представляющей значение анимации.  
  
```  
CAnimationVariable m_value;  
```  
  
##  <a name="operator_double"></a>CAnimationValue::operator DOUBLE  
 Обеспечивает преобразование между CAnimationValue и DOUBLE.  
  
```  
operator DOUBLE();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение анимации.  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает преобразование между CAnimationValue и DOUBLE. Этот метод внутренним образом вызывает GetValue и не проверяет наличие ошибок. При сбое GetValue, возвращаемое значение будет содержать значение по умолчанию, заданные в конструкторе или с SetDefaultValue ранее.  
  
##  <a name="operator_int32"></a>CAnimationValue::operator INT32  
 Обеспечивает преобразование между CAnimationValue и INT32.  
  
```  
operator INT32();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение анимации как целое число.  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает преобразование между CAnimationValue и INT32. Этот метод внутренним образом вызывает GetValue и не проверяет наличие ошибок. При сбое GetValue, возвращаемое значение будет содержать значение по умолчанию, заданные в конструкторе или с SetDefaultValue ранее.  
  
##  <a name="operator_eq"></a>CAnimationValue::operator =  
 Присваивает значение типа DOUBLE CAnimationValue.  
  
```  
void operator=(DOUBLE dblVal);  
void operator=(INT32 nVal);
```  
  
### <a name="parameters"></a>Параметры  
 `dblVal`  
 Указывает значение, присваиваемое значение анимации.  
  
 `nVal`  
 Указывает значение, присваиваемое значение анимации.  
  
### <a name="remarks"></a>Примечания  
 Присваивает значение типа DOUBLE CAnimationValue. Это значение как значение по умолчанию для переменной инкапсулированный анимации. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо повторно включить эти события.  
  
##  <a name="setdefaultvalue"></a>CAnimationValue::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Параметры  
 `dblDefaultValue`  
 Указывает значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать значение по умолчанию. Значение по умолчанию возвращается приложению при анимации не была запущена и/или базового COM-объекта не был создан. Если основной COM-объект, содержащийся в CAnimationVarible уже был создан, этот метод повторно создает ее, таким образом может потребоваться повторный вызов методов EnableValueChanged/EnableIntegerValueChanged.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
