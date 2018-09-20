---
title: Класс SimpleClassFactory | Документация Майкрософт
ms.custom: ''
ms.date: 09/7/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4a3e262567927b818072c1e05acd18aa64cbaa6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446521"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory - класс

Предоставляет основной механизм для создания базового класса.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Параметры

*Base*<br/>
Базовый класс.

## <a name="remarks"></a>Примечания

Базовый класс должен предоставлять конструктор по умолчанию.

В следующем примере кода демонстрируется использование `SimpleClassFactory` с [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос.

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

## <a name="createinstance"></a>Метод SimpleClassFactory::CreateInstance

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

SimpleClassFactory не поддерживает агрегирование. Если поддерживается агрегирование и создаваемый объект был частью агрегата, *pUnkOuter* должен быть указателем на управляющий `IUnknown` интерфейс агрегатной функции.

*riid*<br/>
Идентификатор интерфейса объекта, который требуется создать.

*ppvObject*<br/>
После завершения операции, указатель на экземпляр объекта, заданного параметром *riid* параметра.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если `__WRL_STRICT__` будет определен, Ошибка утверждения создается, если базовый класс, указанный в параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением ClassicCom или WinRtClassicComMix [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.
