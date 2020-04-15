---
title: Класс CAtlWinModule
ms.date: 11/04/2016
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
ms.openlocfilehash: 40385fd592563837546b483bb80978cde6a56555
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321276"
---
# <a name="catlwinmodule-class"></a>Класс CAtlWinModule

Этот класс обеспечивает поддержку компонентов оконирования ATL.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Конструктор.|
|[CAtlWinModule::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Добавляет объект данных.|
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Возвращает указатель на объект данных оконного модуля.|

## <a name="remarks"></a>Remarks

Этот класс обеспечивает поддержку для всех классов ATL, которые требуют функций оконного окна.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData

Этот метод инициализирует и добавляет структуру. `_AtlCreateWndData`

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Параметры

*Pdata*<br/>
Указатель на `_AtlCreateWndData` структуру, которая должна быть инициализирована и добавлена к текущему модулю.

*pObject*<br/>
Указатель на объект **этот** указатель.

### <a name="remarks"></a>Remarks

Этот метод называет [СятВинМодульНадСоздатьВОнДДат,](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) который инициализирует [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуру. Эта структура будет хранить **этот** указатель, используемый для получения экземпляра класса в процедурах окна.

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule

Конструктор.

```
CAtlWinModule();
```

### <a name="remarks"></a>Remarks

В случае сбоя инициализации повышается **EXCEPTION_NONCONTINUABLE** исключение.

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>CAtlWinModule::

Деструктор

```
~CAtlWinModule();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData

Этот метод возвращает указатель `_AtlCreateWndData` в структуру.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `_AtlCreateWndData` структуру, ранее добавленную [cAtlWinModule::AddCreateWndData](#addcreatewnddata)или NULL, если объект недоступен.

## <a name="see-also"></a>См. также раздел

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
