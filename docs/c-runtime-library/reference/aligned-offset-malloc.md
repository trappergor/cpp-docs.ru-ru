---
title: _aligned_offset_malloc
ms.date: 11/04/2016
api_name:
- _aligned_offset_malloc
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
ms.openlocfilehash: 3e8d6f839f3c675b7543ff14f3f633b0c7d5151f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943860"
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

*size*<br/>
Размер запрошенного выделения памяти.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, который был выделен, или **значение NULL** , если операция завершилась ошибкой.

## <a name="remarks"></a>Примечания

**_aligned_offset_malloc** полезен в ситуациях, когда для вложенного элемента требуется выравнивание. Например, если для вложенного класса требуется выравнивание.

**_aligned_offset_malloc** основан на **malloc**; Дополнительные сведения см. в разделе [malloc](malloc.md).

**_aligned_offset_malloc** `__declspec(noalias)` помечается `__declspec(restrict)`и, что означает, что функция гарантированно не изменяет глобальные переменные и что возвращаемый указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

Эта **функция устанавливает** **еномем** в случае сбоя выделения памяти или если запрошенный размер был больше **_HEAP_MAXREQ**. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr". Кроме того, **_aligned_offset_malloc** проверяет свои параметры. Если параметр *alignment* не является степенью 2 или *смещение* больше или равно *размеру* и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **значение NULL** **и устанавливает для** **еинвал**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
