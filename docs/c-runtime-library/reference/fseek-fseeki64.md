---
title: "fseek, _fseeki64 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0d0c0bf620f1b89b9decceed3db9434dae4f9437
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64
Перемещает файловый указатель в указанное местоположение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
 `offset`  
 Количество байт начиная с `origin`.  
  
 `origin`  
 Первоначальная позиция.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если операция завершилась удачно, `fseek` и `_fseeki64` возвращают 0. В противном случае возвращается ненулевое значение. Для устройств, которые не поддерживают поиск, возвращаемое значение не определено. Если `stream` принимает указатель NULL или если `origin` не является одним из описанных ниже допустимых значений, `fseek` и `_fseeki64` вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают -1.  
  
## <a name="remarks"></a>Примечания  
 `fseek` И `_fseeki64` функции перемещает указатель файла (если таковые имеются) связанный с `stream` в новое расположение, `offset` байтов из `origin`. Следующая операция в потоке происходит в новом местоположении. В потоке, открытом для обновления, следующая операция может быть либо операцией чтения, либо операцией записи. Аргумент origin должен быть одной из следующих констант, определенных в STDIO.H:  
  
 `SEEK_CUR`  
 Текущая позиция файлового указателя.  
  
 `SEEK_END`  
 Конец файла.  
  
 `SEEK_SET`  
 Начало файла.  
  
 С помощью функций `fseek` и `_fseeki64` можно переместить указатель в любое место в файле. Указатель также может быть размещен за пределами файла. `fseek`и `_fseeki64` очищает индикатор end of file и Инвертирует результат любого предыдущего `ungetc` вызывает от `stream`.  
  
 Когда файл открыт для добавления данных, текущая позиция в файле определяется последней операцией ввода-вывода, а не тем, где должна произойти следующая запись. Если в открытом для добавления файле еще не было ни одной операции ввода-вывода, этой позицией является начало файла.  
  
 Для потоков, открытых в текстовом режиме `fseek` и `_fseeki64` ограничены использования, поскольку может привести к переводы перевода строки возврата каретки и перевода `fseek` и `_fseeki64` к непредвиденным результатам. Единственным `fseek` и `_fseeki64` операции гарантированно работать над потоками, открытые в текстовом режиме:  
  
-   поиск со смещением 0 относительно любого из значений origin;  
  
-   Поиск с начала файла значение смещения возвращается из вызова `ftell` при использовании `fseek` или `_ftelli64` при использовании `_fseeki64`.  
  
 Кроме того, в текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения/записи, функция `fopen` и все связанные с ней подпрограммы проверяют наличие символа CTRL+Z в конце файла и удаляют его, если это возможно. Это связано с тем, что использование сочетания функций `fseek` и `ftell` или `_fseeki64` и `_ftelli64` для перемещения в файле, который заканчивается символом CTRL+Z, может вызвать неправильное поведение функции `fseek` или `_fseeki64` рядом с концом файла.  
  
 Когда CRT открывает файл, который начинается с метки порядка байтов (BOM), указатель файла помещается после метки (т. е. в начале фактического содержимого файла). Если требуется использовать `fseek` для перехода к началу файла, получите первоначальную позицию с помощью `ftell`, и используйте `fseek` для перехода к этой позиции, а не к позиции 0.  
  
 Эта функция блокирует работу других потоков во время выполнения, поэтому она потокобезопасна. Описание неблокирующей версии этой функции см. в разделе [_fseek_nolock, _fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
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
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, _ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)
