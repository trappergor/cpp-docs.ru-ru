---
title: Глобальные переменные ATL | Документация Майкрософт
ms.custom: ''
ms.date: 12/06/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f32ff38008e55e656bf8901541ffc5ec7246bed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085996"
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
