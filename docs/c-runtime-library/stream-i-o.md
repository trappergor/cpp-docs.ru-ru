---
title: "Потоковый ввод-вывод | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- I/O routines, stream I/O
- I/O [CRT], stream
- stream I/O
ms.assetid: dc7874d3-a91b-456a-9015-4748bb358217
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f342fb51cf2a1e97afa28db710fbb966b31a386b
ms.lasthandoff: 03/30/2017

---
# <a name="stream-io"></a>Потоковый ввод-вывод
Эти функции обрабатывают данные различных размеров и форматов, — от одного символа до больших структур данных. Они также предоставляют возможность буферизации, которая может повысить производительность. Размер буфера потока по умолчанию составляет 4 КБ. Эти подпрограммы влияют только на буферы, созданные подпрограммами библиотеки времени выполнения, и не затрагивают буферы, созданные операционной системой.  
  
### <a name="stream-io-routines"></a>Потоковые подпрограммы ввода-вывода  
  
|Подпрограмма|Применение|  
|-------------|---------|  
|[clearerr](../c-runtime-library/reference/clearerr.md), [clearerr_s](../c-runtime-library/reference/clearerr-s.md)|Очистка индикатора ошибки для потока|  
|[fclose](../c-runtime-library/reference/fclose-fcloseall.md)|Закрытие потока|  
|[_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)|Закрытие всех открытых потоков, кроме `stdin`, `stdout` и `stderr`|  
|[_fdopen, wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Связывание потока с дескриптором открытого файла|  
|[feof](../c-runtime-library/reference/feof.md)|Проверка файла или потока на предмет конца|  
|[ferror](../c-runtime-library/reference/ferror.md)|Проверка на наличие ошибки в потоке|  
|[fflush](../c-runtime-library/reference/fflush.md)|Сброс потока в буфер или на запоминающее устройство|  
|[fgetc, fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md)|Считывание символа из потока (функциональные версии `getc` и `getwc`)|  
|[_fgetchar, _fgetwchar](../c-runtime-library/reference/fgetc-fgetwc.md)|Считать символ из `stdin` (функциональные версии `getchar` и `getwchar`)|  
|[fgetpos](../c-runtime-library/reference/fgetpos.md)|Получение индикатора позиции потока|  
|[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)|Считывание строки из потока|  
|[_fileno](../c-runtime-library/reference/fileno.md)|Получение дескриптора файла, связанного с потоком|  
|[_flushall](../c-runtime-library/reference/flushall.md)|Сброс всех потоков в буфер или запоминающее устройство|  
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Открытие потока|  
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Запись форматированных данных в поток|  
|[fputc, fputwc](../c-runtime-library/reference/fputc-fputwc.md)|Запись символа в поток (функциональные версии `putc` и `putwc`)|  
|[_fputchar, _fputwchar](../c-runtime-library/reference/fputc-fputwc.md)|Запись символа в `stdout` (функциональные версии `putchar` и `putwchar`)|  
|[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)|Запись строки в поток|  
|[fread](../c-runtime-library/reference/fread.md)|Считывание неформатированных данных из потока|  
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Переназначение потокового указателя `FILE` , чтобы он указывал на новый файл или устройство|  
|[fscanf, fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Считывание форматированных данных из потока|  
|[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)|Перемещение позиции в файле в заданное место|  
|[fsetpos](../c-runtime-library/reference/fsetpos.md)|Задание индикатора позиции в потоке|  
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Открытие потока с совместным доступом к файлу|  
|[ftell, _ftelli64](../c-runtime-library/reference/ftell-ftelli64.md)|Получение текущей позиции в файле|  
|[fwrite](../c-runtime-library/reference/fwrite.md)|Запись неформатированных элементов данных в поток|  
|[getc, getwc](../c-runtime-library/reference/getc-getwc.md)|Считывание символа из потока (версии-макросы `fgetc` и `fgetwc`)|  
|[getchar, getwchar](../c-runtime-library/reference/getc-getwc.md)|Считывание символа из `stdin` (версии-макросы `fgetchar` и `fgetwchar`)|  
|[_getmaxstdio](../c-runtime-library/reference/getmaxstdio.md)|Возвращает количество одновременно открытых файлов, допустимое на уровне потокового ввода-вывода.|  
|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|Считывание строки из `stdin`|  
|[_getw](../c-runtime-library/reference/getw.md)|Считывание двоичного числа `int` из потока|  
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Запись форматированных данных в `stdout`|  
|[putc, putwc](../c-runtime-library/reference/putc-putwc.md)|Запись символа в поток (версии-макросы `fputc` и `fputwc`)|  
|[putchar, putwchar](../c-runtime-library/reference/putc-putwc.md)|Запись символа в `stdout` (версии-макросы `fputchar` и `fputwchar`)|  
|[puts, _putws](../c-runtime-library/reference/puts-putws.md)|Запись строки в поток|  
|[_putw](../c-runtime-library/reference/putw.md)|Запись двоичного числа `int` в поток|  
|[rewind](../c-runtime-library/reference/rewind.md)|Перемещение позиции в файле в начало потока|  
|[_rmtmp](../c-runtime-library/reference/rmtmp.md)|Удаление временных файлов, созданных `tmpfile`|  
|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Считывание форматированных данных из `stdin`|  
|[setbuf](../c-runtime-library/reference/setbuf.md)|Управление потоковой буферизацией|  
|[_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)|Задание максимального числа одновременно открытых файлов на уровне потокового ввода-вывода|  
|[setvbuf](../c-runtime-library/reference/setvbuf.md)|Управление потоковой буферизацией и размером буфера|  
|[_snprintf, _snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Запись форматированных данных указанной длины в строку|  
|[_snscanf, _snwscanf](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md), [_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Считывают форматированные данные указанной длины из стандартного входного потока.|  
|[sprintf, swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Запись форматированных данных в строку|  
|[sscanf, swscanf](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md), [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Считывание форматированных данных из строки|  
|[_tempnam, _wtempnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|Создание временного имени файла в заданном каталоге|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md), [tmpfile_s](../c-runtime-library/reference/tmpfile-s.md)|Создание временного файла|  
|[tmpnam, _wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), [tmpnam_s, _wtmpnam_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Создание временного имени файла|  
|[ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)|Отправка символа обратно в поток|  
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md), [_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Вывод форматированных данных на консоль|  
|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|Запись форматированных данных в поток|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), [vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|Запись форматированных данных в `stdout`|  
|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md), [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Запись форматированных данных указанной длины в буфер|  
|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md), [vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Запись форматированных данных в буфер|  
  
 Когда программа начинает выполнение, код запуска автоматически открывает несколько потоков: стандартный ввода (на который указывает `stdin`), стандартный вывода (на который указывает `stdout`) и стандартный вывода ошибок (на который указывает `stderr`). Эти потоки по умолчанию направляются на консоль (клавиатуру и экран). С помощью `freopen` можно перенаправить `stdin`, `stdout`или `stderr` на файл на диске или на устройство.  
  
 Файлы, открытые с помощью потоковых подпрограмм, по умолчанию буферизуются. Функции `stdout` и `stderr` сбрасываются, когда они полны или — при записи в символьное устройство — после каждого вызова библиотеки. Если программа завершается аварийно, буферы вывода могут не быть сброшены, что приводит к потере данных. С помощью `fflush` или `_flushall` можно гарантировать, что буфер, связанный с заданным файлом, или все открытые буферы будут сброшены в операционную систему, которая может кэшировать данные перед их записью на диск. Функция фиксации на диск гарантирует, что сброшенное содержимое буфера не потеряется в случае сбоя системы.  
  
 Существует два способа сохранить зафиксировать содержимое буфера на диске:  
  
-   Скомпоновать код с файлом COMMODE.OBJ, чтобы установить глобальный флаг фиксации. По умолчанию этот глобальный флаг имеет значение `n`, т. е. "не фиксировать".  
  
-   Установите флаг режима в `c` с помощью `fopen` или `_fdopen`.  
  
 Любой файл, открытый с флагом `c` или `n` , ведет себя в соответствии со значением флага, вне зависимости от состояния глобального флага фиксации.  
  
 Если программа не закрывает поток явно, поток автоматически закроется, когда завершится выполнение программы. Следует, однако, закрывать поток, когда программа завершает работу с ним, так как количество потоков, которые могут одновременно быть открыты, ограничено. Дополнительные сведения об этом ограничении см. в описании функции [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md).  
  
 Ввод может следовать сразу за выводом только с промежуточным вызовом `fflush` или функции позиционирования в файле (`fseek`, `fsetpos`или `rewind`). Вывод может следовать за вводом без промежуточного вызова функции позиционирования в файле, если операция ввода обнаруживает конец файла.  
  
## <a name="see-also"></a>См. также  
 [Ввод и вывод](../c-runtime-library/input-and-output.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
