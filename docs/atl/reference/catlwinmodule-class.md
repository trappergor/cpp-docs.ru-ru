---
title: Класс Катлвинмодуле
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
ms.openlocfilehash: 5cdf13ebbb982ad8184a52dcf1a3e30d71e4e5b0
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167712"
---
# <a name="catlwinmodule-class"></a>Класс Катлвинмодуле

Этот класс обеспечивает поддержку для компонентов окна ATL.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлвинмодуле:: Катлвинмодуле](#catlwinmodule)|Конструктор.|
|[Катлвинмодуле:: ~ Катлвинмодуле](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлвинмодуле:: Аддкреатевнддата](#addcreatewnddata)|Добавляет объект данных.|
|[Катлвинмодуле:: Екстракткреатевнддата](#extractcreatewnddata)|Возвращает указатель на объект данных модуля окна.|

## <a name="remarks"></a>Remarks

Этот класс обеспечивает поддержку для всех классов ATL, для которых требуются функции для окон.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>Катлвинмодуле:: Аддкреатевнддата

Этот метод инициализирует и добавляет `_AtlCreateWndData` структуру.

```cpp
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Указатель на `_AtlCreateWndData` структуру, которая должна быть инициализирована и добавлена в текущий модуль.

*Объект*<br/>
Указатель на **этот** указатель объекта.

### <a name="remarks"></a>Remarks

Этот метод вызывает [атлвинмодулеаддкреатевнддата](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) , который инициализирует структуру [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) . Эта структура будет хранить **этот** указатель, используемый для получения экземпляра класса в процедурах окна.

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>Катлвинмодуле:: Катлвинмодуле

Конструктор.

```cpp
CAtlWinModule();
```

### <a name="remarks"></a>Remarks

Если инициализация завершается неудачей, возникает исключение **EXCEPTION_NONCONTINUABLE** .

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>Катлвинмодуле:: ~ Катлвинмодуле

Деструктор

```cpp
~CAtlWinModule();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>Катлвинмодуле:: Екстракткреатевнддата

Этот метод возвращает указатель на `_AtlCreateWndData` структуру.

```cpp
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `_AtlCreateWndData` структуру, ранее добавленную с помощью [Катлвинмодуле:: аддкреатевнддата](#addcreatewnddata), или значение null, если объект недоступен.

## <a name="see-also"></a>См. также

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
