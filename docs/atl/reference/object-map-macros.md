---
title: Макрос карты объектов
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 66a418019ba506a5832c8e3ad86a3764c1186df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326218"
---
# <a name="object-map-macros"></a>Макрос карты объектов

Эти макросы определяют карты объектов и записи.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Позволяет указать текстовое описание объекта класса, которое будет внесено в карту объекта.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Вводит объект ATL в карту объекта, обновляет реестр и создает экземпляр объекта.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="declare_object_description"></a><a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION

Позволяет указать текстовое описание объекта класса.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Описание объекта класса.

### <a name="remarks"></a>Remarks

ATL вводит это описание в карту объекта через [макрос OBJECT_ENTRY_AUTO.](#object_entry_auto)

DECLARE_OBJECT_DESCRIPTION реализует `GetObjectDescription` функцию, которую можно использовать для переопределения метода [CComCoClass::GetObjectDescription.](ccomcoclass-class.md#getobjectdescription)

Функция `GetObjectDescription` вызывается `IComponentRegistrar::GetComponents`. `IComponentRegistrar`— это интерфейс автоматизации, позволяющий регистрировать и отменять отдельные компоненты в DLL. При создании объекта регистратора компонентов с помощью AtL Project Wizard `IComponentRegistrar` мастер автоматически реализует интерфейс. `IComponentRegistrar`обычно используется сервером транзакций Майкрософт.

Для получения дополнительной информации о ATL [Creating an ATL Project](../../atl/reference/creating-an-atl-project.md)проект Мастера, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

## <a name="object_entry_auto"></a><a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO

Вводит объект ATL в карту объекта, обновляет реестр и создает экземпляр объекта.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
(в) CLSID класса COM, реализованный классом СЗ под названием *класс.*

*class*<br/>
(в) Название класса СЗ, реализующего класс COM, представленное *clsid.*

### <a name="remarks"></a>Remarks

Макросы записи объекта помещаются в глобальной области видимости в проекте для поддержки регистрации, инициализации и создания класса.

OBJECT_ENTRY_AUTO вводит функции указателей класса создателя и `CreateInstance` функции класса-фабрики-создателя для этого объекта в авторскую карту объектов ATL. Когда [называется CAtlComModule::RegisterServer,](catlcommodule-class.md#registerserver) он обновляет системный реестр для каждого объекта на карте объектов.

В приведенной ниже таблице описывается, как информация, добавленная в карту объекта, получена из класса, данного в качестве второго параметра к этому макросу.

|Информация для|Получено от|
|---------------------|-------------------|
|Регистрация COM|[Реестр Макрос](../../atl/reference/registry-macros.md)|
|Создание фабрики класса|[Класс Фабрика Макрос](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Создание экземпляров|[Макрос агрегации](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Регистрация категории компонентов|[Категория Макрос](../../atl/reference/category-macros.md)|
|Инициализация и очистка уровня класса|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

## <a name="object_entry_non_createable_ex_auto"></a><a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
(в) CLSID класса COM, реализованный классом СЗ под названием *класс.*

*class*<br/>
(в) Название класса СЗ, реализующего класс COM, представленное *clsid.*

### <a name="remarks"></a>Remarks

Макросы записи объекта помещаются в глобальной области видимости в проекте для поддержки регистрации, инициализации и создания класса.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO позволяет указать, что объект должен быть [OBJECT_ENTRY_AUTO](#object_entry_auto) зарегистрирован и инициализирован (см. `CoCreateInstance`OBJECT_ENTRY_AUTO для получения дополнительной информации), но он не должен быть доступен через .

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
