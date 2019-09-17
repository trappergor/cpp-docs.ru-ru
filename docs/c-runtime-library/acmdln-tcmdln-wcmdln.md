---
title: _acmdln, _tcmdln, _wcmdln
ms.date: 11/04/2016
api_name:
- _wcmdln
- _acmdln
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
ms.openlocfilehash: 07061244e06256341a6da7d04e5487e81c4b9378
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940620"
---
# <a name="_acmdln-_tcmdln-_wcmdln"></a>_acmdln, _tcmdln, _wcmdln

Внутренняя глобальная переменная CRT. Командная строка.

## <a name="syntax"></a>Синтаксис

```
char * _acmdln;
wchar_t * _wcmdln;

#ifdef WPRFLAG
   #define _tcmdln _wcmdln
#else
   #define _tcmdln _acmdln
```

## <a name="remarks"></a>Примечания

Эти внутренние переменные CRT хранят полную командную строку. Они предоставляются в экспортируемых символах для CRT, но не предназначены для использования в коде. `_acmdln` хранит данные как строку символов. `_wcmdln` хранит данные как строку расширенных символов. `_tcmdln` может быть определена как `_acmdln` или`_wcmdln` в зависимости от обстоятельств.

## <a name="see-also"></a>См. также

[Глобальные переменные](../c-runtime-library/global-variables.md)
