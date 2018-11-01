---
title: Глобальные переменные ATL
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 4f98b31d2454b7c6e903e5b5b87bceb4ddcb6961
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498323"
---
# <a name="atl-global-variables"></a>Глобальные переменные ATL

## <a name="patlmodule"></a>_pAtlModule

Глобальная переменная, сохранения указателя для текущего модуля.

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>Примечания

Методы этой глобальной переменной можно использовать для предоставления функций, который был указан (устаревшая) класс CComModule в Visual C++ 6.0.

### <a name="example"></a>Пример

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>Требования

**Заголовок:** atlbase.h
