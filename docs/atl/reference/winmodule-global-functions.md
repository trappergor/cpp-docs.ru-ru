---
title: Глобальные функции Винмодуле
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 1a929fd0f583150e84ce5b1efa7e896bc16e4247
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229939"
---
# <a name="winmodule-global-functions"></a>Глобальные функции Винмодуле

Эти функции обеспечивают поддержку `_AtlCreateWndData` операций структуры.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>атлвинмодулеаддкреатевнддата

Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Параметры

*пвинмодуле*<br/>
Указатель на структуру [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) модуля.

*pData*<br/>
Указатель на структуру [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) для инициализации и добавления в текущий модуль.

*Объект*<br/>
Указатель на **`this`** указатель объекта.

### <a name="remarks"></a>Remarks

Инициализирует `_AtlCreateWndData` структуру, которая используется для хранения **`this`** указателя, используемого для ссылки на экземпляры класса, и добавляет его в список, на который ссылается структура модуля `_ATL_WIN_MODULE70` . Вызывается методом [катлвинмодуле:: аддкреатевнддата](catlwinmodule-class.md#addcreatewnddata).

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>атлвинмодуликстракткреатевнддата

Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Параметры

*пвинмодуле*<br/>
Указатель на структуру [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) модуля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на структуру [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) .

### <a name="remarks"></a>Remarks

Эта функция извлекает существующую `_AtlCreateWndData` структуру из списка, на который ссылается `_ATL_WIN_MODULE70` Структура модуля.

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
