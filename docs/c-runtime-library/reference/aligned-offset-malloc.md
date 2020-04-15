---
title: _aligned_offset_malloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_malloc
- _o__aligned_offset_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 1f13afbab75d2926d1c642c1430a3ffe5ecbac8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350588"
---
# <a name="_aligned_offset_malloc"></a>_aligned_offset_malloc

Размещение памяти на указанной границе выравнивания.

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
Размер запрошенного выделения памяти.

*выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*Смещение*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, который был выделен или **NULL,** если операция не удалась.

## <a name="remarks"></a>Remarks

**_aligned_offset_malloc** полезен в ситуациях, когда выравнивание необходимо на вложенном элементе; например, если выравнивание необходимо для вложенного класса.

**_aligned_offset_malloc** основанна на **malloc**; для получения дополнительной информации, см [Malloc](malloc.md).

**_aligned_offset_malloc** `__declspec(noalias)` отмечени `__declspec(restrict)`и, что означает, что функция гарантированно не изменяет глобальные переменные и что указатель возвращается не псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

Эта функция устанавливает **errno** к **ENOMEM,** если распределение памяти не удалось или если запрашиваемый размер был **больше,** чем _HEAP_MAXREQ . Для получения дополнительной информации о **errno**, см [Errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, **_aligned_offset_malloc** проверяет свои параметры. Если *выравнивание* не является силой 2 или если *смещение* больше или равно *размеру* и ненулевой, эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция возвращает **NULL** и устанавливает **errno** **в EINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также раздел

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
