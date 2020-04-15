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
ms.openlocfilehash: a55412eff18fd04ac4e41c0f001991c1cf725b9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321511"
---
# <a name="catlbasemodule-class"></a>Класс CAtlBaseModule

Этот класс мгновенно используется в каждом проекте ATL.

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
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Добавляет экземпляр ресурса в список сохраненных ручек.|
|[CAtlBaseModule::GetHinstanceAt](#gethinstanceat)|Возвращает ручку в указанный экземпляр ресурса.|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Возвращает экземпляр модуля с `CAtlBaseModule` объекта.|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Возвращает экземпляр ресурса `CAtlBaseModule` из объекта.|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Удаляет экземпляр ресурса из списка сохраненных ручек.|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Устанавливает экземпляр ресурса `CAtlBaseModule` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Переменная, указывают, не удалось ли инициализация модуля.|

## <a name="remarks"></a>Remarks

Экземпляр названного `CAtlBaseModule` _AtlBaseModule присутствует в каждом проекте ATL, содержащий ручку к экземпляру модуля, ручку модуля, содержащую ресурсы (которые по умолчанию являются одним и тем же), и массив ручек модулей, предоставляющих первичные ресурсы. `CAtlBaseModule`можно безопасно получить из нескольких потоков.

Этот класс заменяет устаревший класс [CComModule,](../../atl/reference/ccommodule-class.md) используемый в более ранних версиях ATL.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance

Добавляет экземпляр ресурса в список сохраненных ручек.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Параметры

*hInst*<br/>
Экземпляр ресурса для добавления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если ресурс был успешно добавлен, ложно в противном случае.

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>CAtlBaseModule::CAtlBaseModule

Конструктор.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>Remarks

Создает объект `CAtlBaseModule`.

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>CAtlBaseModule::GetHinstanceAt

Возвращает ручку в указанный экземпляр ресурса.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>Параметры

*Я*<br/>
Число экземпляра ресурса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в экземпляр ресурса или NULL, если не существует соответствующего экземпляра ресурса.

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance

Возвращает экземпляр модуля с `CAtlBaseModule` объекта.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает экземпляр модуля.

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance

Возвращает экземпляр ресурса.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает экземпляр ресурса.

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a>CAtlBaseModule::m_bInitFailed

Переменная, указывают, не удалось ли инициализация модуля.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>Remarks

Правда, если модуль инициализирован, ложный, если он не смог инициализировать.

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance

Удаляет экземпляр ресурса из списка сохраненных ручек.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Параметры

*hInst*<br/>
Экземпляр ресурса для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если ресурс был успешно удален, ложно в противном случае.

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance

Устанавливает экземпляр ресурса `CAtlBaseModule` объекта.

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Параметры

*hInst*<br/>
Новый экземпляр ресурса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный экземпляр ресурса.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
