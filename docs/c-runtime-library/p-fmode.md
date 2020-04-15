---
title: __p__fmode
ms.date: 4/2/2020
api_name:
- __p__fmode
- _o___p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: aecba640099719f90db8bbd5dbe386ea99aae45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349250"
---
# <a name="__p__fmode"></a>__p__fmode

Указывает на глобальную переменную `_fmode`, которая определяет значение *режима трансляции файлов* по умолчанию для операций ввода-вывода файлов.

## <a name="syntax"></a>Синтаксис

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на глобальную переменную `_fmode`.

## <a name="remarks"></a>Remarks

Функция `__p__fmode` предназначена только для внутреннего пользования и не должна вызываться из кода пользователя.

Режим трансляции файлов определяет трансляцию `binary` или `text` для операций ввода-вывода [_open](../c-runtime-library/reference/open-wopen.md) и [_pipe](../c-runtime-library/reference/pipe.md). Дополнительные сведения см. в разделе [_fmode](../c-runtime-library/fmode.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__p\__fmode|stdlib.h|
