---
title: fseek, _fseeki64 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fseeki64
- fseek
apilocation:
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 266eb1589c97b177057e6a72874261c745acb475
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64

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

*offset*<br/>
Количество байт, начиная с *origin*.

*origin*<br/>
Первоначальная позиция.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **fseek** и **_fseeki64** возвращает 0. В противном случае возвращается ненулевое значение. Для устройств, которые не поддерживают поиск, возвращаемое значение не определено. Если *поток* является пустым указателем, или, если *источника* не является одним из допустимых значений, описанных ниже **fseek** и **_fseeki64** вызова недопустим Обработчик параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают -1.

## <a name="remarks"></a>Примечания

**Fseek** и **_fseeki64** функции перемещает указатель файла (если таковые имеются) связанный с *поток* в новое расположение, *смещение* байт из *источника*. Следующая операция в потоке происходит в новом местоположении. В потоке, открытом для обновления, следующая операция может быть либо операцией чтения, либо операцией записи. Аргумент *источника* должен быть одним из следующих констант, определенных в STDIO. H:

|Начальное значение|Значение|
|-|-|
**SEEK_CUR**|Текущая позиция файлового указателя.
**SEEK_END**|Конец файла.
**SEEK_SET**|Начало файла.

Можно использовать **fseek** и **_fseeki64** для изменения положения указателя мыши в любом месте в файле. Указатель также может быть размещен за пределами файла. **fseek** и **_fseeki64** очищает индикатор end of file и Инвертирует результат любого предыдущего [ungetc](ungetc-ungetwc.md) вызывает от *поток*.

Когда файл открыт для добавления данных, текущая позиция в файле определяется последней операцией ввода-вывода, а не тем, где должна произойти следующая запись. Если в открытом для добавления файле еще не было ни одной операции ввода-вывода, этой позицией является начало файла.

Для потоков, открытых в текстовом режиме **fseek** и **_fseeki64** ограничены использования, поскольку может привести к переводы перевода строки возврата каретки и перевода **fseek** и **_ fseeki64** к непредвиденным результатам. Единственным **fseek** и **_fseeki64** операции гарантированно работать над потоками, открытые в текстовом режиме:

- поиск со смещением 0 относительно любого из значений origin;

- Поиск с начала файла значение смещения возвращается из вызова [ftell](ftell-ftelli64.md) при использовании **fseek** или [_ftelli64](ftell-ftelli64.md) при использовании **_fseeki64**.

Кроме того, в текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или записи [fopen](fopen-wfopen.md) и все связанные с ней подпрограммы проверяют наличие символа CTRL + Z в конце файла и удаляют его, если это возможно. Это делается потому, что использование сочетания **fseek** и [ftell](ftell-ftelli64.md) или **_fseeki64** и [_ftelli64](ftell-ftelli64.md)для перемещения в файле, который заканчивается CTRL + Z может привести к **fseek** или **_fseeki64** неправильное поведение ближе к концу файла.

Когда CRT открывает файл, который начинается с метки порядка байтов (BOM), указатель файла помещается после метки (т. е. в начале фактического содержимого файла). Если вам требуется **fseek** в начало файла используйте [ftell](ftell-ftelli64.md) для получения начальное положение и **fseek** к нему, а не к позиции 0.

Эта функция блокирует работу других потоков во время выполнения, поэтому она потокобезопасна. Описание неблокирующей версии этой функции см. в разделе [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
