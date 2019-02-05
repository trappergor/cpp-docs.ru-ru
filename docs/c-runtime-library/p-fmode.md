---
title: __p__fmode
ms.date: 11/04/2016
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: bdb390ef5ae7254c463a3abd66860559cebeeeb9
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703055"
---
# <a name="pfmode"></a>__p__fmode

Указывает на глобальную переменную `_fmode`, которая определяет значение *режима трансляции файлов* по умолчанию для операций ввода-вывода файлов.

## <a name="syntax"></a>Синтаксис

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на глобальную переменную `_fmode`.

## <a name="remarks"></a>Примечания

Функция `__p__fmode` предназначена только для внутреннего пользования и не должна вызываться из кода пользователя.

Режим трансляции файлов определяет трансляцию `binary` или `text` для операций ввода-вывода [_open](../c-runtime-library/reference/open-wopen.md) и [_pipe](../c-runtime-library/reference/pipe.md). Дополнительные сведения см. в разделе [_fmode](../c-runtime-library/fmode.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__p\__fmode|stdlib.h|