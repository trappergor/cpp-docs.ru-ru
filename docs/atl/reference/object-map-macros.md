---
title: Макросы схемы объекта | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b85d157cd6124bb0ef6e6167a415c018e14b046
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040444"
---
# <a name="object-map-macros"></a>Макросы сопоставления объектов

Эти макросы определяют сопоставления объектов и записи.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Позволяет указать объект класса текстовое описание, которое будет введено в карте объектов.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Вводит объект ATL в карте объектов, обновляет реестр и создает экземпляр объекта.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.|  

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="declare_object_description"></a>  DECLARE_OBJECT_DESCRIPTION

Можно указать описание для объекта класса.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Описание класса объекта.

### <a name="remarks"></a>Примечания

ATL вводит это описание в карте объектов через [OBJECT_ENTRY_AUTO](#object_entry_auto) макрос.

Реализует DECLARE_OBJECT_DESCRIPTION `GetObjectDescription` функцию, которую можно использовать для переопределения [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) метод.  

`GetObjectDescription` Функция вызывается из `IComponentRegistrar::GetComponents`. `IComponentRegistrar` представляет собой интерфейс автоматизации для регистрации и отмены регистрации отдельных компонентов в библиотеке DLL. При создании объекта регистрации компонента с помощью мастера проектов ATL, мастер будет автоматически реализовывать `IComponentRegistrar` интерфейс. `IComponentRegistrar` обычно используется сервером транзакций.

Дополнительные сведения о мастере проекта ATL, см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

##  <a name="object_entry_auto"></a>  OBJECT_ENTRY_AUTO

Вводит объект ATL в карте объектов, обновляет реестр и создает экземпляр объекта.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
[in] CLSID объекта COM-класса, реализованного в классе C++ с именем *класс*.

*class*<br/>
[in] Имя класса C++, реализующего класс COM, представленный *clsid*.

### <a name="remarks"></a>Примечания

Макросы записи объекта помещаются в глобальной области видимости в проекте для поддержки регистрации, инициализации и создания класса.

OBJECT_ENTRY_AUTO вводит указатели функций класс создателя и класс создателя фабрики класса `CreateInstance` функции для данного объекта в карте объектов ATL автоматически созданный. Когда [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) является именем, он обновляет системного реестра для каждого объекта в карте объектов.  

В следующей таблице описывается способ получения информации, добавлен новый объект из класса, присвоенный данного макроса в качестве второго параметра.

|Сведения для|Полученный из|
|---------------------|-------------------|
|Регистрация COM|[Макросы реестра](../../atl/reference/registry-macros.md)|
|Создание фабрики класса|[Макросы фабрики класса](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Создание экземпляра|[Макросы агрегирования](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Регистрации категории компонентов|[Макросы категорий](../../atl/reference/category-macros.md)|
|Уровня класса инициализации и очистки|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

##  <a name="object_entry_non_createable_ex_auto"></a>  OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Позволяет указать, что объект должен быть зарегистрирован и инициализирован, но не должен создаваться внешне через `CoCreateInstance`.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
[in] CLSID объекта COM-класса, реализованного в классе C++ с именем *класс*.

*class*<br/>
[in] Имя класса C++, реализующего класс COM, представленный *clsid*.

### <a name="remarks"></a>Примечания

Макросы записи объекта помещаются в глобальной области видимости в проекте для поддержки регистрации, инициализации и создания класса.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO позволяет указать, что зарегистрирован объект и они будут инициализированы (см. в разделе [OBJECT_ENTRY_AUTO](#object_entry_auto) Дополнительные сведения), но не должен создаваться внешне через `CoCreateInstance`.

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
