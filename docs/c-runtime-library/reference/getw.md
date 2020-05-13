---
title: _getw
ms.date: 4/2/2020
api_name:
- _getw
- _o__getw
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: fc1dfcc54259dfe40d2fc37be1e1c0ab63ab7c4a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916311"
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

## <a name="remarks"></a>Remarks

Функция **_getw** считывает следующее двоичное значение типа **int** из файла, связанного с *потоком Stream* , и увеличивает связанный указатель файла (если таковой имеется), чтобы он указывал на следующий непрочтенный символ. **_getw** не предполагает никакого особого выравнивания элементов в потоке. Проблемы с переносом могут возникать с **_getw** , так как размер типа **int** и порядок байтов в типе **int** различаются в разных системах.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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
