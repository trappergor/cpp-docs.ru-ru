---
title: Класс Platform::Agile
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- AGILE/Platform::Platform
- AGILE/Platform::Platform::Agile::Agile
- AGILE/Platform::Platform::Agile::Get
- AGILE/Platform::Platform::Agile::GetAddressOf
- AGILE/Platform::Platform::Agile::GetAddressOfForInOut
- AGILE/Platform::Platform::Agile::Release
helpviewer_keywords:
- Platform::Agile
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
ms.openlocfilehash: d39270b7bf05e820ea376a40310abeb8add2c5ad
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742961"
---
# <a name="platformagile-class"></a>Класс Platform::Agile

Представляет объект, имеющий MashalingBehavior = Standard, как объект Agile, который значительно снижает вероятность возникновения в среде выполнения исключений, связанных с потоками. `Agile<T>` позволяет объекту, отличному от Agile, вызывать тот же или другой поток или быть вызванным из этих потоков. Дополнительные сведения см. в разделе Работа [с потоками и маршалирование](../cppcx/threading-and-marshaling-c-cx.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class Agile;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа для класса, отличного от Agile.

### <a name="remarks"></a>Remarks

Большинство классов в среда выполнения Windows являются гибкими. Объект Agile может вызывать внутрипроцессный или внепроцессный объект либо быть вызванным таким объектом в том же или другом потоке. Если объект не является объектом гибкой разработки, заключите его в объект `Agile<T>` , который является объектом гибкой разработки. После этого объект `Agile<T>` можно маршалировать, используя таким образом базовый объект, отличный от Agile.

Класс `Agile<T>` — это стандартный класс неуправляемого кода C++, для которого требуется включаемый файл `agile.h`. Он представляет объект, отличный от Agile, и *контекст*объекта Agile. Контекст задает потоковую модель объекта Agile и поведение маршалинга. Операционная система использует контекст для определения способа маршалирования объекта.

### <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Agile:: Agile](#ctor)|Инициализирует новый экземпляр класса Agile.|
|[Деструктор Agile::~Agile](#dtor)|Ликвидирует текущий экземпляр класса Agile.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Agile::Get](#get)|Возвращает дескриптор объекта, представленного текущим объектом Agile.|
|[Agile::GetAddressOf](#getaddressof)|Повторно инициализирует текущий объект Agile и возвращает адрес дескриптора для объекта типа `T`.|
|[Agile::GetAddressOfForInOut](#getaddressofforinout)|Возвращает адрес дескриптора объекта, представленного текущим объектом Agile.|
|[Agile::Release](#release)|Отменяет базовый объект и контекст текущего объекта Agile.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Agile:: operator->](#operator-arrow)|Извлекает дескриптор объекта, представленного текущим объектом Agile.|
|[Agile::operator=](#operator-assign)|Присваивает указанное значение текущему объекту Agile.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Object`

`Agile`

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Заголовок:** agile.h

## <a name="agileagile-constructor"></a><a name="ctor"></a> Конструктор Agile:: Agile

Инициализирует новый экземпляр класса Agile.

### <a name="syntax"></a>Синтаксис

```cpp
Agile();
Agile(T^ object);
Agile(const Agile<T>& object);
Agile(Agile<T>&& object);
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип, указанный в параметре имени типа шаблона.

*object*<br/>
Во второй версии данного конструктора: объект, используемый для инициализации нового экземпляра класса Agile. В третьей версии: объект, который копируется в новый экземпляр класса Agile. В четвертой версии: объект, который перемещается в новый экземпляр класса Agile.

### <a name="remarks"></a>Remarks

Первая версия этого конструктора является конструктором по умолчанию. Вторая версия инициализирует новый экземпляра класса Agile из объекта, указанного параметром `object`. Третья версия является конструктором копирования. Четвертая версия является конструктором перемещения. Этот конструктор не может вызывать исключения.

## <a name="agileagile-destructor"></a><a name="dtor"></a> Динамический деструктор:: ~ Agile

Ликвидирует текущий экземпляр класса Agile.

### <a name="syntax"></a>Синтаксис

```cpp
~Agile();
```

### <a name="remarks"></a>Remarks

Этот деструктор также освобождает объект, представленный текущим объектом Agile.

## <a name="agileget-method"></a><a name="get"></a> Метод Agile:: Get

Возвращает дескриптор объекта, представленного текущим объектом Agile.

### <a name="syntax"></a>Синтаксис

```cpp
T^ Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор объекта, представленного текущим объектом Agile.

Тип возвращаемого значения фактически является скрытым внутренним типом. Удобным способом удержания возвращаемого значения является присвоение его переменной, объявленной с **`auto`** ключевым словом выведения типа. Например, `auto x = myAgileTvariable->Get();`.

## <a name="agilegetaddressof-method"></a><a name="getaddressof"></a> Метод Agile:: GetAddressOf

Повторно инициализирует текущий объект Agile и возвращает адрес дескриптора для объекта типа `T`.

### <a name="syntax"></a>Синтаксис

```cpp
T^* GetAddressOf() throw();
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип, указанный в параметре имени типа шаблона.

### <a name="return-value"></a>Возвращаемое значение

Адрес дескриптора для объекта типа `T`.

### <a name="remarks"></a>Remarks

Эта операция освобождает текущее представление объекта типа `T` при его наличии, повторно инициализирует данные-члены объекта Agile, получает текущий контекст потока, а затем возвращает адрес переменной дескриптора для объекта, который может представлять объект, отличный от Agile. Чтобы экземпляр класса Agile предоставлял объект, используйте оператор присваивания ([Agile:: operator =](#operator-assign)), чтобы назначить объект экземпляру класса Agile.

## <a name="agilegetaddressofforinout-method"></a><a name="getaddressofforinout"></a> Метод Agile:: GetAddressOfForInOut

Возвращает адрес дескриптора объекта, представленного текущим объектом Agile.

### <a name="syntax"></a>Синтаксис

```cpp
T^* GetAddressOfForInOut()  throw();
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип, указанный в параметре имени типа шаблона.

### <a name="return-value"></a>Возвращаемое значение

Адрес дескриптора объекта, представленного текущим объектом Agile.

### <a name="remarks"></a>Remarks

Эта операция получает текущий контекст потоков, затем возвращает адрес дескриптора основного объекта.

## <a name="agilerelease-method"></a><a name="release"></a> Метод Agile:: Release

Отменяет базовый объект и контекст текущего объекта Agile.

### <a name="syntax"></a>Синтаксис

```cpp
void Release() throw();
```

### <a name="remarks"></a>Remarks

Выполняется отмена базового объекта и контекста текущего объекта Agile, если они существуют, а затем значению объекта Agile присваивается NULL.

## <a name="agileoperator-gt-operator"></a><a name="operator-arrow"></a>Оператор Agile:: operator- &gt;

Извлекает дескриптор объекта, представленного текущим объектом Agile.

### <a name="syntax"></a>Синтаксис

```cpp
T^ operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор объекта, представленного текущим объектом Agile.

Этот оператор фактически возвращает скрытый внутренний тип. Удобным способом удержания возвращаемого значения является присвоение его переменной, объявленной с **`auto`** ключевым словом выведения типа.

## <a name="agileoperator-operator"></a><a name="operator-assign"></a> Оператор Agile:: operator =

Присваивает указанный объект текущему объекту Agile.

### <a name="syntax"></a>Синтаксис

```cpp
Agile<T> operator=( T^ object ) throw();
Agile<T> operator=( const Agile<T>& object ) throw();
Agile<T> operator=( Agile<T>&& object ) throw();
T^ operator=( IUnknown* lp ) throw();
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип, указанный в имени типа шаблона.

*object*<br/>
Объект или дескриптор объекта, который копируется или перемещается в текущий объект Agile.

*LP*<br/>
Указатель интерфейса IUnknown объекта.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для объекта типа `T`

### <a name="remarks"></a>Remarks

Первая версия оператора присваивания копирует дескриптор ссылочного типа в текущий объект Agile. Вторая версия копирует ссылку на тип Agile в текущий объект Agile. Третья версия перемещает тип Agile в текущий объект Agile. Четвертая версия перемещает указатель на COM-объект в текущий объект Agile.

Операция присваивания автоматически сохраняет контекст текущего объекта Agile.

## <a name="see-also"></a>См. также

[Пространство имен платформы](platform-namespace-c-cx.md)
