---
title: Глобальные функции WinModule
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 0e7450ea2a42c0b35dc5a6d1b77dfb0f2acb9520
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265094"
---
# <a name="winmodule-global-functions"></a>Глобальные функции WinModule

Эти функции обеспечивают поддержку `_AtlCreateWndData` структуры операций.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atlwinmoduleaddcreatewnddata"></a>  AtlWinModuleAddCreateWndData

Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Параметры

*pWinModule*<br/>
Указатель на модуль [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) структуры.

*pData*<br/>
Указатель на [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры для инициализации и добавления к текущему модулю.

*pObject*<br/>
Указатель на объект **это** указатель.

### <a name="remarks"></a>Примечания

Инициализирует `_AtlCreateWndData` структуру, которая используется для хранения **это** указатель используется для обращения к экземплярам класса и добавляет его в список, ссылаются модуля `_ATL_WIN_MODULE70` структуры. Вызывается средой [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).

##  <a name="atlwinmoduleextractcreatewnddata"></a>  AtlWinModuleExtractCreateWndData

Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Параметры

*pWinModule*<br/>
Указатель на модуль [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры.

### <a name="remarks"></a>Примечания

Эта функция будет извлечения существующей `_AtlCreateWndData` структуру из списка ссылается модуля `_ATL_WIN_MODULE70` структуры.

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
