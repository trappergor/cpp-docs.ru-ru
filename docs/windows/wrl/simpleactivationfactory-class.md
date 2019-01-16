---
title: SimpleActivationFactory - класс
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 1831a816d0967c2ca53f941128639ea368c1b727
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337691"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory - класс

Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Параметры

*Base*<br/>
Базовый класс.

## <a name="remarks"></a>Примечания

Базовый класс должен предоставлять конструктор по умолчанию.

В следующем примере кода демонстрируется использование SimpleActivationFactory с [ActivatableClassWithFactoryEx](activatableclass-macros.md) макрос.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод SimpleActivationFactory::ActivateInstance](#activateinstance)|Создает экземпляр указанного интерфейса.|
|[Метод SimpleActivationFactory::GetRuntimeClassName](#getruntimeclassname)|Получает имя класса среды выполнения экземпляра класса, указанного параметром *базы* параметре шаблона класса.|
|[Метод SimpleActivationFactory::GetTrustLevel](#gettrustlevel)|Получает уровень доверия выполняемого экземпляра класса, указанного параметром *базы* параметре шаблона класса.|

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

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="activateinstance"></a>Метод SimpleActivationFactory::ActivateInstance

Создает экземпляр указанного интерфейса.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Параметры

*ppvObject*<br/>
После завершения операции, указатель на экземпляр объекта, заданного параметром `Base` параметре шаблона класса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если `__WRL_STRICT__` будет определен, Ошибка утверждения создается, если базовый класс, указанный в параметре шаблона класса не является производным от [RuntimeClass](runtimeclass-class.md), или не настроен со значением WinRt или WinRtClassicComMix [ RuntimeClassType](runtimeclasstype-enumeration.md) значение перечисления.

## <a name="getruntimeclassname"></a>Метод SimpleActivationFactory::GetRuntimeClassName

Получает имя класса среды выполнения экземпляра класса, указанного в параметре шаблона класса `Base`.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Параметры

*runtimeName*<br/>
После завершения операции представляет имя класса среды выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если `__WRL_STRICT__` будет определен, Ошибка утверждения создается, если класс, указанный `Base` параметре шаблона класса не является производным от [RuntimeClass](runtimeclass-class.md), или не настроен со значением WinRt или WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) значение перечисления.

## <a name="gettrustlevel"></a>Метод SimpleActivationFactory::GetTrustLevel

Получает уровень доверия выполняемого экземпляра класса, указанного параметром `Base` параметре шаблона класса.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Параметры

*trustLvl*<br/>
После завершения операции, уровень доверия текущего объекта класса.

### <a name="return-value"></a>Возвращаемое значение

Всегда значение S_OK.
