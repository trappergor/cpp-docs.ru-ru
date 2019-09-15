---
title: _getw
ms.date: 11/04/2016
api_name:
- _getw
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: ad03c92ce90542ecae13609ee228ad094f64fc07
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954881"
---
# <a name="_getw"></a>_getw

Получает значение типа integer из потока.

## <a name="syntax"></a>Синтаксис

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**_getw** возвращает считанное целочисленное значение. Возвращаемое значение **EOF** указывает на ошибку или конец файла. Однако поскольку значение **EOF** также является допустимым целым числом, используйте **feof** или **ferror** для проверки состояния конца файла или ошибки. Если *Stream* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** задается значение, а функция возвращает **EOF**.

## <a name="remarks"></a>Примечания

Функция **_getw** считывает следующее двоичное значение типа **int** из файла, связанного с *потоком Stream* , и увеличивает связанный указатель файла (если таковой имеется), чтобы он указывал на следующий непрочтенный символ. **_getw** не предполагает никакого особого выравнивания элементов в потоке. Проблемы с переносом могут возникать с **_getw** , так как размер типа **int** и порядок байтов в типе **int** различаются в разных системах.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getw.c
// This program uses _getw to read a word
// from a stream, then performs an error check.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   int i;

   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )
      printf( "Couldn't open file\n" );
   else
   {
      // Read a word from the stream:
      i = _getw( stream );

      // If there is an error...
      if( ferror( stream ) )
      {
         printf( "_getw failed\n" );
         clearerr_s( stream );
      }
      else
         printf( "First data word in file: 0x%.4x\n", i );
      fclose( stream );
   }
}
```

### <a name="input-crt_getwtxt"></a>Входные данные: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
