---
title: __p__commode
ms.date: 11/04/2016
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: 3a565a179077635438c03539cefa83823603bb00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482712"
---
# <a name="pcommode"></a>__p__commode

Указывает на глобальную переменную `_commode`, которая определяет значение *режима фиксации файлов* по умолчанию для операций ввода-вывода файлов.

## <a name="syntax"></a>Синтаксис

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на глобальную переменную `_commode`.

## <a name="remarks"></a>Примечания

Функция `__p__commode` предназначена только для внутреннего пользования и не должна вызываться из кода пользователя.

Режим фиксации файлов указывает, когда на диск записываются критические данные. Дополнительные сведения см. в разделе [fflush](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__p\__commode|internal.h|