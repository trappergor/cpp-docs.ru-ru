---
title: ClassFactory - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: 3b738cc8f439e6653162ab99b0a26e87aa8fee36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372668"
---
# <a name="classfactory-class"></a>ClassFactory - класс

Реализует базовую функциональность интерфейса `IClassFactory`.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Интерфейс нулевой.

*I1*<br/>
Первый интерфейс.

*I2*<br/>
Второй интерфейс.

## <a name="remarks"></a>Remarks

Используйте `ClassFactory` для обеспечения реализации завода, определяемого пользователем.

Следующий шаблон программирования демонстрирует, как использовать структуру [Implements](implements-structure.md) для указания более трех интерфейсов на фабрике класса.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                        | Описание
------------------------------------------- | -----------
[Класс-фабрика::КлассФабрика](#classfactory) |

### <a name="public-methods"></a>Открытые методы

Имя                                            | Описание
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[КлассFactory::AddRef](#addref)                 | Приращения отсчета ссылок на текущий `ClassFactory` объект.
[Класс-Фабрика:LockServer](#lockserver)         | Приращения или уменьшение количества основных объектов, отслеживаемых текущим `ClassFactory` объектом.
[КлассНаяфабрика::Квиинтерфейс](#queryinterface) | Извлекает указатель на интерфейс, указанный по параметру.
[КлассНаяфабрика::Освобождение](#release)               | Декретирует значение отсчета `ClassFactory` ссылок для текущего объекта.

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

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="classfactoryaddref"></a><a name="addref"></a>КлассFactory::AddRef

Приращения отсчета ссылок на текущий `ClassFactory` объект.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a>Класс-фабрика::КлассФабрика

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a>Класс-Фабрика:LockServer

Приращения или уменьшение количества основных объектов, отслеживаемых текущим `ClassFactory` объектом.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*Стадо*<br/>
**true** приращения числа отслеживаемых объектов. **ложное** для уничтожения числа отслеживаемых объектов.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение E_FAIL.

### <a name="remarks"></a>Remarks

`ClassFactory`отслеживает объекты в базовом экземпляре класса [Модуль.](module-class.md)

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a>КлассНаяфабрика::Квиинтерфейс

Извлекает указатель на интерфейс, указанный по параметру.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
Когда эта операция завершается, указатель на интерфейс, указанный по параметру *riid.*

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="classfactoryrelease"></a><a name="release"></a>КлассНаяфабрика::Освобождение

Декретирует значение отсчета `ClassFactory` ссылок для текущего объекта.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.
