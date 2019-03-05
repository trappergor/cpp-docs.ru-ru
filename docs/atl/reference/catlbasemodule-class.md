---
title: Класс CAtlBaseModule
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: d382d1fe7d50a2fdeefc9b477625580792de7d6f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284766"
---
# <a name="catlbasemodule-class"></a>Класс CAtlBaseModule

В каждом проекте ATL создается экземпляр этого класса.

## <a name="syntax"></a>Синтаксис

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Добавляет экземпляр ресурса в список хранимых маркеров.|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Возвращает дескриптор экземпляра указанного ресурса.|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Возвращает экземпляр модуля из `CAtlBaseModule` объекта.|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Возвращает экземпляр ресурса из `CAtlBaseModule` объекта.|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Удаляет экземпляр ресурса из списка хранимых маркеров.|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Задает экземпляр ресурса `CAtlBaseModule` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Переменная, которая указывает, если ошибка инициализации модуля.|

## <a name="remarks"></a>Примечания

Экземпляр `CAtlBaseModule` именованный _AtlBaseModule присутствует в каждом проекте ATL, содержащий дескриптор экземпляра модуля, дескриптор модуля, содержащего ресурсы (которые по умолчанию, один и тот же) и массив дескрипторов для модулей, предоставляя первичный ресурсы. `CAtlBaseModule` безопасного доступа из нескольких потоков.

Этот класс заменяет устаревшее [CComModule](../../atl/reference/ccommodule-class.md) класс, используемый в более ранних версиях ATL.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance

Добавляет экземпляр ресурса в список хранимых маркеров.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Параметры

*hInst*<br/>
Добавьте экземпляр ресурса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если ресурс был успешно добавлен, значение false, в противном случае образом.

##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule

Конструктор.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>Примечания

Создает объект `CAtlBaseModule`.

##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt

Возвращает дескриптор экземпляра указанного ресурса.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>Параметры

*i*<br/>
Номер экземпляра ресурса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор экземпляра ресурса, или значение NULL, если существует без соответствующего экземпляра ресурса.

##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance

Возвращает экземпляр модуля из `CAtlBaseModule` объекта.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает экземпляр модуля.

##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance

Возвращает экземпляр ресурса.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает экземпляр ресурса.

##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed

Переменная, которая указывает, если ошибка инициализации модуля.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>Примечания

Значение true, если модуль инициализирован, false, если ей не удалось инициализировать.

##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance

Удаляет экземпляр ресурса из списка хранимых маркеров.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Параметры

*hInst*<br/>
Удаляемый экземпляр ресурса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если ресурс успешно удален, и false в противном случае.

##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance

Задает экземпляр ресурса `CAtlBaseModule` объекта.

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Параметры

*hInst*<br/>
Новый экземпляр ресурса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает экземпляр обновленный ресурс.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Модульные классы](../../atl/atl-module-classes.md)
