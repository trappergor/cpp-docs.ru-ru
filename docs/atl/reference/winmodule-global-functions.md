---
title: Глобальные функции WinModule
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 3d7d001a2835514cc5385a7069c0bcda58cdd88e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329363"
---
# <a name="winmodule-global-functions"></a>Глобальные функции WinModule

Эти функции `_AtlCreateWndData` обеспечивают поддержку операций структуры.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData

Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Параметры

*pWinModule*<br/>
Указатель на [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) структуру модуля.

*Pdata*<br/>
Указатель на [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуру, которая будет инициализирована и добавлена к текущему модулю.

*pObject*<br/>
Указатель на объект **этот** указатель.

### <a name="remarks"></a>Remarks

Инициализирует структуру, `_AtlCreateWndData` которая используется для хранения **этого** указателя, используемого для обозначения экземпляров `_ATL_WIN_MODULE70` класса, и добавляет его в список, на который ссылается структура модуля. Вызывается [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData

Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Параметры

*pWinModule*<br/>
Указатель на [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) структуру модуля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуру.

### <a name="remarks"></a>Remarks

Эта функция будет `_AtlCreateWndData` извлекать существующую структуру из `_ATL_WIN_MODULE70` списка, на который ссылается структура модуля.

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
