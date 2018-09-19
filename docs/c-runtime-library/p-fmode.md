---
title: __p__fmode | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
apitype: DLLExport
f1_keywords:
- __p__fmode
dev_langs:
- C++
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c4dcea9e3f35bf5fd8dbfbed9273562ac3db551
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056343"
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