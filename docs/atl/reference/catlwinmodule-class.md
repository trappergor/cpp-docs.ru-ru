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
ms.openlocfilehash: d0bc98fa48f84e67ab38106dea3fe22d5ad1757d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857355"
---
# <a name="catlwinmodule-class"></a>Класс Катлвинмодуле

Этот класс обеспечивает поддержку для компонентов окна ATL.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Катлвинмодуле:: Катлвинмодуле](#catlwinmodule)|Конструктор.|
|[Катлвинмодуле:: ~ Катлвинмодуле](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
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

##  <a name="addcreatewnddata"></a>Катлвинмодуле:: Аддкреатевнддата

Этот метод инициализирует и добавляет структуру `_AtlCreateWndData`.

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Указатель на структуру `_AtlCreateWndData` для инициализации и добавления в текущий модуль.

*Объект*<br/>
Указатель на **этот** указатель объекта.

### <a name="remarks"></a>Remarks

Этот метод вызывает [атлвинмодулеаддкреатевнддата](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) , который инициализирует структуру [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) . Эта структура будет хранить **этот** указатель, используемый для получения экземпляра класса в процедурах окна.

##  <a name="catlwinmodule"></a>Катлвинмодуле:: Катлвинмодуле

Конструктор.

```
CAtlWinModule();
```

### <a name="remarks"></a>Remarks

Если инициализация завершается неудачей, возникает исключение **EXCEPTION_NONCONTINUABLE** .

##  <a name="dtor"></a>Катлвинмодуле:: ~ Катлвинмодуле

Деструктор

```
~CAtlWinModule();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

##  <a name="extractcreatewnddata"></a>Катлвинмодуле:: Екстракткреатевнддата

Этот метод возвращает указатель на структуру `_AtlCreateWndData`.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `_AtlCreateWndData` структуру, ранее добавленную с помощью [катлвинмодуле:: аддкреатевнддата](#addcreatewnddata), или значение null, если объект недоступен.

## <a name="see-also"></a>См. также раздел

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
