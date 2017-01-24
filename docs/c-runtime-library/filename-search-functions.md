---
title: "Функции поиска имени файла | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "имена файлов [C++], поиск"
  - "Функция _find"
  - "Функция wfind"
  - "Функция find"
  - "Функция _wfind"
ms.assetid: 2bc2f8ef-44e4-4271-b3e8-666d36fde828
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Функции поиска имени файла
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти функции осуществляют и завершают поиск для указанных имен файлов:  
  
-   [\_findnext, \_wfindnext](../Topic/_findnext,%20_findnext32,%20_findnext32i64,%20_findnext64,%20_findnext64i32,%20_findnexti64,%20_wfindnext,%20_wfindnext32,%20_wfindnext32i64,%20_wfindnext64,%20_wfindnext64i32,%20_wfindnexti64.md)  
  
-   [\_findfirst, \_wfindfirst](../Topic/_findfirst,%20_findfirst32,%20_findfirst32i64,%20_findfirst64,%20_findfirst64i32,%20_findfirsti64,%20_wfindfirst,%20_wfindfirst32,%20_wfindfirst32i64,%20_wfindfirst64,%20_wfindfirst64i32,%20_wfindfirsti64.md)  
  
-   [\_findclose](../c-runtime-library/reference/findclose.md)  
  
## Заметки  
 Функция `_findfirst` предоставляет сведения о первом экземпляре имени файла, соответствующем файлу, указанному в аргументе `filespec`. В `filespec` можно использовать любые комбинации подстановочных знаков, которые поддерживаются операционной системой.  
  
 Функции возвращают сведения о файле в структуре `finddata_t`, которая определена в IO.h. Различные функции в данном семействе используют множество вариантов структуры `_finddata_t`. Базовая структура `_finddata_t` содержит следующие элементы:  
  
 `unsigned attrib`  
 Атрибут файла.  
  
 `time_t time_create`  
 Время создания файла \(–1L для файловых систем FAT\). Это время хранится в формате UTC. Для преобразования в местное время используйте функцию [localtime\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
 `time_t time_access`  
 Время последнего доступа к файлу \(–1L для файловых систем FAT\). Это время хранится в формате UTC. Для преобразования в местное время используйте функцию `localtime_s`.  
  
 `time_t time_write`  
 Время последней записи в файл. Это время хранится в формате UTC. Для преобразования в местное время используйте функцию `localtime_s`.  
  
 `_fsize_t size`  
 Длина файла в байтах.  
  
 `char name`\[ `_MAX_PATH`\]  
 Имя соответствующего файла или каталога, с конечным нуль\-символом, без пути.  
  
 В файловых системах, которые не поддерживают время создания и последнего обращения к файлу \(например, в системе FAT\), поля `time_create` и `time_access` всегда содержат значение –1L.  
  
 `_MAX_PATH` определен в Stdlib.h как 260 байт.  
  
 Задание целевых атрибутов \(например `_A_RDONLY`\) для ограничения операции поиска невозможно. Эти атрибуты возвращаются в поле `attrib` структуры `_finddata_t` и могут иметь следующие значения \(определенные в IO.h\). Пользователи не должны считать эти значения единственно возможными для поля `attrib`.  
  
 `_A_ARCH`  
 Архив. Устанавливается при изменении файла и очищается командой **BACKUP**. Значение: 0x20.  
  
 `_A_HIDDEN`  
 Скрытый файл. Обычно не виден команде DIR, если не используется параметр **\/AH**. Возвращает сведения об обычных файлах и файлах, имеющих этот атрибут. Значение: 0x02.  
  
 `_A_NORMAL`  
 Нормальный. У файла не установлены никакие другие атрибуты, чтение и запись возможны без ограничений. Значение: 0x00.  
  
 `_A_RDONLY`  
 Только для чтения. Файл невозможно открыть для записи; также невозможно создать файл с этим именем. Значение: 0x01.  
  
 `_A_SUBDIR`  
 Подкаталог. Значение: 0x10.  
  
 `_A_SYSTEM`  
 Системный файл. Обычно не виден команде **DIR**, если не используется параметр **\/A** или **\/A:S**. Значение: 0x04.  
  
 Функция `_findnext` находит следующее имя, если таковое имеется, которое соответствует аргументу `filespec`, указанному в предыдущем вызове функции `_findfirst`. Аргумент `fileinfo` должен указывать на структуру, инициализированную предыдущим вызовом функции `_findfirst`. Если обнаружено соответствие, содержимое структуры `fileinfo` изменяется, как описано выше. В противном случае оно остается неизменным. Функция `_findclose` закрывает указанный дескриптор поиска и освобождает все связанные ресурсы для функций `_findfirst` и `_findnext`. Дескриптор, возвращенный ранее функцией `_findfirst` или `_findnext`, необходимо сначала передать в функцию `_findclose`, чтобы можно было выполнять операции изменения \(например, удаление\) в каталогах, которые образуют переданные им пути.  
  
 Функции `_find` допускают вложение. Например, если вызов функции `_findfirst` или `_findnext` нашел файл, являющийся подкаталогом, новый поиск можно начать другим вызовом функции `_findfirst` или `_findnext`.  
  
 `_wfindfirst` и `_wfindnext` — это версии функций `_findfirst` и `_findnext` для расширенных символов. Аргумент структуры версий для расширенных символов имеет тип данных `_wfinddata_t`, который определен в файлах IO.h и Wchar.h. Поля этого типа данных совпадают с полями типа данных `_finddata_t`, за исключением того, что в `_wfinddata_t` поле имени имеет тип `wchar_t`, а не тип `char`. В остальном поведение функций `_wfindfirst` и `_wfindnext` не отличается от поведения функций `_findfirst` и `_findnext`.  
  
 Функции `_findfirst` и `_findnext` используют 64\-разрядный тип времени. Если необходимо использовать прежний 32\-разрядный тип времени, можно определить `_USE_32BIT_TIME_T`. Версии этих функций, в именах которых имеется суффикс `32`, используют 32\-разрядный тип времени; версии с суффиксом `64` используют 64\-разрядный тип времени.  
  
 Функции `_findfirst32i64`, `_findnext32i64`, `_wfindfirst32i64` и `_wfindnext32i64` также ведут себя идентично версиям этих функций с 32\-разрядным типом времени, за исключением того, что они используют и возвращают 64\-разрядные значения длины файлов. Функции `_findfirst64i32`, `_findnext64i32`, `_wfindfirst64i32` и `_wfindnext64i32`используют 64\-разрядный тип времени, но 32\-разрядные значения длины файлов. Эти функции используют соответствующие варианты типа `_finddata_t`, в которых поля имеют разные типы для времени и размера файла.  
  
 `_finddata_t` фактически представляет собой макрос, который преобразуется в `_finddata64i32_t` \(или `_finddata32_t`, если определена константа `_USE_32BIT_TIME_T`\). В следующей таблице приведены сводные сведения об этих вариантах `_finddata_t`:  
  
|Структура|Тип времени|Тип размера файла|  
|---------------|-----------------|-----------------------|  
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|  
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|  
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|`__int64`|  
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|`__int64`|  
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|  
  
 `_fsize_t` представляет собой `typedef` для `unsigned long` \(32 бита\).  
  
## Пример  
  
```  
// crt_find.c // This program uses the 32-bit _find functions to print // a list of all files (and their attributes) with a .C extension // in the current directory. #include <stdio.h> #include <stdlib.h> #include <io.h> #include <time.h> int main( void ) { struct _finddata_t c_file; intptr_t hFile; // Find first .c file in current directory if( (hFile = _findfirst( "*.c", &c_file )) == -1L ) printf( "No *.c files in current directory!\n" ); else { printf( "Listing of .c files\n\n" ); printf( "RDO HID SYS ARC  FILE         DATE %25c SIZE\n", ' ' ); printf( "--- --- --- ---  ----         ---- %25c ----\n", ' ' ); do { char buffer[30]; printf( ( c_file.attrib & _A_RDONLY ) ? " Y  " : " N  " ); printf( ( c_file.attrib & _A_HIDDEN ) ? " Y  " : " N  " ); printf( ( c_file.attrib & _A_SYSTEM ) ? " Y  " : " N  " ); printf( ( c_file.attrib & _A_ARCH )   ? " Y  " : " N  " ); ctime_s( buffer, _countof(buffer), &c_file.time_write ); printf( " %-12s %.24s  %9ld\n", c_file.name, buffer, c_file.size ); } while( _findnext( hFile, &c_file ) == 0 ); _findclose( hFile ); } }  
```  
  
```Output  
Перечень C-файлов RDO HID SYS ARC  FILE         DATE                           SIZE --- --- --- ---  ----         ----                           ---- N   N   N   Y   blah.c       ср, 13 фев 2002 09:21:42       1715 N   N   N   Y   test.c       ср, 06 фев 2002 14:30:44        312  
```  
  
## См. также  
 [Системные вызовы](../Topic/System%20Calls.md)