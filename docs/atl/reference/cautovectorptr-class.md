---
title: Класс CAutoVectorPtr
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: fc4bd4ba7a2f41a25679f1da718671f525519708
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748214"
---
# <a name="cautovectorptr-class"></a>Класс CAutoVectorPtr

Этот класс представляет собой интеллектуальный объект указателя с использованием новых векторных и удаленных операторов.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Конструктор.|
|[CAutoVectorPtr::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::Выделение](#allocate)|Вызов иметод, чтобы выделить память, требуемую `CAutoVectorPtr`массивом объектов, на которые указывается.|
|[CAutoVectorPtr::Attach](#attach)|Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.|
|[CAutoVectorPtr::Detach](#detach)|Вызовите этот метод, чтобы освободить право собственности на указатель.|
|[CAutoVectorPtr::Бесплатно](#free)|Вызовите этот метод, чтобы `CAutoVectorPtr`удалить объект, на который указывает .|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::оператор T](#operator_t__star)|Оператор актерского состава.|
|[CAutoVectorPtr::оператор](#operator_eq)|Оператор назначения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::m_p](#m_p)|Переменная данных указателя.|

## <a name="remarks"></a>Remarks

Этот класс предоставляет методы создания и управления интеллектуальным указателем, которые помогут защититься от утечек памяти, автоматически освобождая ресурсы, когда она выпадает из сферы действия. `CAutoVectorPtr`похож на `CAutoPtr`, единственное `CAutoVectorPtr` различие в том, что использует [вектор новых&#91;&#93;](../../standard-library/new-operators.md#op_new_arr) и [вектор удалить&#91;&#93;](../../standard-library/new-operators.md#op_delete_arr) выделить и бесплатную память вместо **новых** и **удалить** операторов. Если требуются классы `CAutoVectorPtr` сбора, обратитесь к [CAutoVectorPtrElementTraitsTraits.](../../atl/reference/cautovectorptrelementtraits-class.md)

На примере использования класса «умный указатель» можно ознакомиться на [CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>CAutoVectorPtr::Выделение

Вызов иметод, чтобы выделить память, требуемую `CAutoVectorPtr`массивом объектов, на которые указывается.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Параметры

*nЭлементы*<br/>
Количество элементов в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает сяпоние, если память успешно выделена, ложная при сбое.

### <a name="remarks"></a>Remarks

В отладочных сборках произойдет сбой утверждения, если переменная [CAutoVectorPtr::m_p](#m_p) в настоящее время указывает на существующее значение; то есть, он не равен NULL.

## <a name="cautovectorptrattach"></a><a name="attach"></a>CAutoVectorPtr::Attach

Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Объект `CAutoVectorPtr` будет владеть этим указателем.

### <a name="remarks"></a>Remarks

Когда `CAutoVectorPtr` объект становится владельцем указателя, он автоматически удаляет указатель и любые выделенные данные, когда он выходит за рамки. Если [cAutoVectorPtr::Detach](#detach) называется, программист снова получает ответственность за освобождение любых выделенных ресурсов.

В отладочных сборках произойдет сбой утверждения, если переменная [CAutoVectorPtr::m_p](#m_p) в настоящее время указывает на существующее значение; то есть, он не равен NULL.

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr

Конструктор.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Существующий указатель.

### <a name="remarks"></a>Remarks

Объект `CAutoVectorPtr` может быть создан с помощью существующего указателя, и в этом случае он передает право собственности на указатель.

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>CAutoVectorPtr::

Деструктор

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы. Вызовы [CAutoVectorPtr::Бесплатно](#free).

## <a name="cautovectorptrdetach"></a><a name="detach"></a>CAutoVectorPtr::Detach

Вызовите этот метод, чтобы освободить право собственности на указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Remarks

Выпускает право собственности на указатель, устанавливает [cAutoVectorPtr::m_p](#m_p) переменной члена null и возвращает копию указателя. После `Detach`вызова программист должен освободить все выделенные ресурсы, за которые `CAutoVectorPtr` объект, возможно, ранее взял на себя ответственность.

## <a name="cautovectorptrfree"></a><a name="free"></a>CAutoVectorPtr::Бесплатно

Вызовите этот метод, чтобы `CAutoVectorPtr`удалить объект, на который указывает .

```cpp
void Free() throw();
```

### <a name="remarks"></a>Remarks

Объект, на который `CAutoVectorPtr` указывается, освобождается, и [cAutoVectorPtr::m_p](#m_p) переменная члена установлена null.

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>CAutoVectorPtr::m_p

Переменная данных указателя.

```
T* m_p;
```

### <a name="remarks"></a>Remarks

Эта переменная члена содержит информацию указателя.

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>CAutoVectorPtr::оператор

Оператор назначения.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на **>CAutoVectorPtr\< **T .

### <a name="remarks"></a>Remarks

Оператор назначения отсоединяет `CAutoVectorPtr` объект от любого текущего указателя и прикрепляет новый указатель, *р,* на своем месте.

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>CAutoVectorPtr::оператор T

Оператор актерского состава.

```
operator T*() const throw();
```

### <a name="remarks"></a>Remarks

Возвращает указатель на тип данных объекта, определенный в шаблоне класса.

## <a name="see-also"></a>См. также раздел

[Класс CAutoPtr](../../atl/reference/cautoptr-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
