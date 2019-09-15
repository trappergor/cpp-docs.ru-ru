---
title: _set_controlfp
ms.date: 04/05/2018
api_name:
- _set_controlfp
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_controlfp
- _set_controlfp
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 4d39406db0f4c9ba6374776da62aea2dbb61e23d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948674"
---
# <a name="_set_controlfp"></a>_set_controlfp

Задает управляющее слово блока операций с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Параметры

*невконтрол*<br/>
Значения битов в новом управляющем слове.

*виде*<br/>
Маска для установки битов нового управляющего слова.

## <a name="return-value"></a>Возвращаемое значение

Нет.

## <a name="remarks"></a>Примечания

Функция **_set_controlfp** похожа на **_control87**, но она устанавливает только управляющее слово с плавающей запятой в *невконтрол*. Биты в значениях показывают состояние элемента управления блоком операций с плавающей запятой. Состояние элемента управления блока операций с плавающей запятой разрешает программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой. Можно также маскировать или отмаскировать исключения с плавающей запятой с помощью **_set_controlfp**. Дополнительные сведения см. в разделе [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md).

Эта функция является устаревшей при компиляции с [параметром/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md) , так как среда CLR поддерживает только точность с плавающей запятой по умолчанию.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Совместимость|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|только для процессоров x86|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
