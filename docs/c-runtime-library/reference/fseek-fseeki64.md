---
title: fseek, _fseeki64
ms.date: 4/2/2020
api_name:
- _fseeki64
- fseek
- _o__fseeki64
- _o_fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: e8f6021a0b770f6b435653c190d5968f9ac50a57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345755"
---
# <a name="fseek-_fseeki64"></a>fseek, _fseeki64

Перемещает файловый указатель в указанное местоположение.

## <a name="syntax"></a>Синтаксис

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

*Смещение*<br/>
Количество байт, начиная с *origin*.

*Происхождения*<br/>
Первоначальная позиция.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха, **fseek** и **_fseeki64** возвращает 0. В противном случае возвращается ненулевое значение. Для устройств, которые не поддерживают поиск, возвращаемое значение не определено. Если *поток* является нулевой указатель, или если *происхождение* не является одним из допустимых значений, описанных ниже, **fseek** и **_fseeki64** ссылаться на недействительный обработчик параметров, как описано в [параметрвалиции](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции устанавливают **errno** к **EINVAL** и возвращают -1.

## <a name="remarks"></a>Remarks

**Функции fseek** и **_fseeki64** перемещает указатель файла (если таковые имеется), связанные с *потоком,* в новое место, которое *компенсируется* байтами от *происхождения.* Следующая операция в потоке происходит в новом местоположении. В потоке, открытом для обновления, следующая операция может быть либо операцией чтения, либо операцией записи. *Происхождение* аргумента должно быть одной из следующих констант, определенных в STDIO. H:

|значение происхождения|Значение|
|-|-|
| **SEEK_CUR** | Текущая позиция файлового указателя. |
| **SEEK_END** | Конец файла. |
| **SEEK_SET** | Начало файла. |

Вы можете использовать **fseek** и **_fseeki64** для того чтобы reposition указатель везде в архиве. Указатель также может быть размещен за пределами файла. **fseek** и **_fseeki64** очищает конечный индикатор и сводит на нет эффект любых предыдущих вызовов [ungetc](ungetc-ungetwc.md) против *потока.*

Когда файл открыт для добавления данных, текущая позиция в файле определяется последней операцией ввода-вывода, а не тем, где должна произойти следующая запись. Если в открытом для добавления файле еще не было ни одной операции ввода-вывода, этой позицией является начало файла.

Для потоков, открытых в текстовом режиме, **fseek** и **_fseeki64** имеют ограниченное использование, потому что переводы кормов возврата каретных линий могут привести к тому, что **fseek** и **_fseeki64** для получения неожиданных результатов. Единственными **операциями fseek** и **_fseeki64,** гарантированно работают на потоках, открытых в текстовом режиме, являются:

- поиск со смещением 0 относительно любого из значений origin;

- Ищу от начала файла с смещенным значением возвращается из вызова в [ftell](ftell-ftelli64.md) при использовании **fseek** или [_ftelli64](ftell-ftelli64.md) при использовании **_fseeki64.**

Кроме того, в текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения/письма, [fopen](fopen-wfopen.md) и всех связанных с ними подпрограмм проверяют CTRL в конце файла и удаляют его, если это возможно. Это делается потому, что с помощью комбинации **fseek** и [ftell](ftell-ftelli64.md) или **_fseeki64** и [_ftelli64,](ftell-ftelli64.md)чтобы переместиться в файл, который заканчивается ctRL, может привести к **fseek** или **_fseeki64** вести себя ненадлежащим образом ближе к концу файла.

Когда CRT открывает файл, который начинается с метки порядка байтов (BOM), указатель файла помещается после метки (т. е. в начале фактического содержимого файла). Если у вас есть, чтобы **придя** к началу файла, используйте [ftell,](ftell-ftelli64.md) чтобы получить исходное положение и **fseek** к нему, а не к позиции 0.

Эта функция блокирует работу других потоков во время выполнения, поэтому она потокобезопасна. Описание неблокирующей версии этой функции см. в разделе [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[Перемотки](rewind.md)<br/>
