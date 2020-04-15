---
title: SimpleClassFactory - класс
ms.date: 09/7/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
ms.openlocfilehash: 924b9d2c30f11e6f0444d9c647807f1c86dcc411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373548"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory - класс

Предоставляет основной механизм для создания базового класса.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Параметры

*Базы*<br/>
Базовый класс.

## <a name="remarks"></a>Remarks

Базовый класс должен предоставить конструктор по умолчанию.

Следующий пример кода демонстрирует, `SimpleClassFactory` как использовать с помощью макроса [ActivatableWithFactoryEx.](activatableclass-macros.md)

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод SimpleClassFactory::CreateInstance](#createinstance)|Создает экземпляр указанного интерфейса.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ClassFactory`

`SimpleClassFactory`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="simpleclassfactorycreateinstance-method"></a><a name="createinstance"></a>SimpleClassFactory::CreateInstance Метод

Создает экземпляр указанного интерфейса.

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>Параметры

*pUnkOuter*<br/>
Должно быть `nullptr`; в противном случае возвращается значение CLASS_E_NOAGGREGATION.

SimpleClassFactory не поддерживает агрегирование. Если агрегация поддерживается и создаваемый объект является частью агрегата, *pUnkOuter* будет указателем на контрольный `IUnknown` интерфейс агрегата.

*riid*<br/>
Идентификатор интерфейса объекта, который требуется создать.

*ppvObject*<br/>
Когда эта операция завершается, указатель на экземпляр объекта, указанный параметром *риида.*

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Remarks

Если `__WRL_STRICT__` определено, ошибка утверждения испускается, если базовый класс, указанный в параметре шаблона класса, не получен из [RuntimeClass](runtimeclass-class.md)или не настроен со значением перечисления ClassicCom или WinRtClassicComMix [RuntimeClassTypeType.](runtimeclasstype-enumeration.md)
