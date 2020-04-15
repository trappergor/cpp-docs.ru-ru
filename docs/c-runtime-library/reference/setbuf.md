---
title: setbuf
ms.date: 4/2/2020
api_name:
- setbuf
- _o_setbuf
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
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: f96cffb8770cda78ebff8d873b441ddc288bc41f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332077"
---
# <a name="setbuf"></a>setbuf

Управляет буферизацией потока. Эта функция не рекомендуется; вместо нее используйте функцию [setvbuf](setvbuf.md) .

## <a name="syntax"></a>Синтаксис

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

*Буфера*<br/>
Выделенный пользователем буфер.

## <a name="remarks"></a>Remarks

Функция **setbuf** управляет буферизацией для *потока.* Аргумент *потока* должен относиться к открытому файлу, который не был прочитан или написан. Если аргумент *буфера* **NULL,** поток не буферный. В противном случае буфер должен указывать на массив символов длины **BUFSI**, где **BUFSI '** является размербуфера, как это определено в STDIO. H. Вместо буфера, по умолчанию выделенного системой для данного потока, для буферизации ввода-вывода используется указанный пользователем буфер. Поток **stderr** не буферизирован по умолчанию, но вы можете использовать **setbuf** для присвоения буферов **stderr.**

**setbuf** был заменен [setvbuf](setvbuf.md), который является предпочтительным рутиной для нового кода. В отличие от **setvbuf,** **setbuf** не имеет возможности сообщать об ошибках. **setvbuf** также позволяет управлять как буферным режимом, так и размером буфера. **setbuf** существует для совместимости с существующим кодом.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
