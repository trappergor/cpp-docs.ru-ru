---
title: setvbuf
ms.date: 4/2/2020
api_name:
- setvbuf
- _o_setvbuf
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: 203265a8dd85854bcedd737359b856fdc4cce04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316262"
---
# <a name="setvbuf"></a>setvbuf

Управляет потоковой буферизацией и размером буфера.

## <a name="syntax"></a>Синтаксис

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

*Буфера*<br/>
Выделенный пользователем буфер.

*Режим*<br/>
Режим буферизации.

*Размер*<br/>
Размер буфера в байтах. Допустимый диапазон: 2 <*размер* <INT_MAX (2147483647). Внутренне значение, поставляемое для *размера,* округляется до ближайшего кратного 2.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха.

Если *поток* **NULL,** или если *режим* или *размер* не находится в пределах допустимого изменения, вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если продолжение выполнения разрешено, эта функция возвращает –1 и задает для **errno** значение **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **setvbuf** позволяет программе контролировать как буферизирование, так и размер буфера для *потока.* *поток* должен относиться к открытому файлу, который не подвергся операции ввоза/входе с момента его открытия. Массив, на который указывает *буфер,* используется в качестве буфера, если он не **является NULL,** и \* в этом случае **setvbuf** использует автоматически выделенный буфер *размера*длины /2 байта.

Режим должен быть **_IOFBF,** **_IOLBF**или **_IONBF.** Если *режим* **_IOFBF** или **_IOLBF,** то *размер* используется в качестве размера буфера. Если *режим* **_IONBF,** поток не буферизирован, а *размер* и *буфер* игнорируются. Значения для *режима* и их значения:

|значение *режима*|Значение|
|-|-|
| **_IOFBF** | Полная буферизация; то есть *буфер* используется в качестве буфера, а *размер* используется как размер буфера. Если *буфер* **NULL,** используется автоматически выделенный *размер* буфера байтами длиной. |
| **_IOLBF** | В некоторых системах таким образом осуществляется линейная буферизация. Однако для Win32 поведение такое же, как **и _IOFBF** - Full Buffering. |
| **_IONBF** | Буфер не используется, независимо от *буфера* или *размера.* |

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
