---
title: Константы доступа чтения и записи файлов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.constants.file
dev_langs:
- C++
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f57ac6ffc3c13c640d7bdf6a2ec64912148bfbc3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391146"
---
# <a name="file-readwrite-access-constants"></a>Константы доступа чтения и записи файлов
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Эти константы определяют запрашиваемый для файла тип доступа ("a", "r" или "w"). В типе доступа можно указать как [режим преобразования](../c-runtime-library/file-translation-constants.md) ("b" или "t"), так и [режим фиксации на диск](../c-runtime-library/commit-to-disk-constants.md) ("c" или "n").  
  
 Типы доступа описаны ниже.  
  
 **"a"**  
 Открывает для записи в конец файла (добавление); сначала создает файл, если он не существует. Все операции записи выполняются в конце файла. Указатель файла можно перемещать с помощью функции `fseek` или **rewind**, но он всегда возвращается в конец файла перед выполнением любой операции записи.  
  
 **"a+"**  
 То же, что и выше, но допускает чтение.  
  
 **"r"**  
 Открывает для чтения. Если файл не существует или его невозможно найти, открытие файла завершается ошибкой.  
  
 **"r+"**  
 Открывает для чтения и записи. Если файл не существует или его невозможно найти, открытие файла завершается ошибкой.  
  
 **"w"**  
 Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.  
  
 **"w+"**  
 Открывает пустой файл для чтения и записи. Если указанный файл существует, его содержимое удаляется.  
  
 Если задан тип доступа "r+", "w+" или "a+", разрешены чтение и запись (считается, что файл открыт "для обновления"). Но при переключении между чтением и записью необходимо использовать промежуточные операции `fflush`, `fsetpos`, `fseek` или **rewind**. Для операции `fsetpos` или `fseek` можно задать текущее положение.  
  
## <a name="see-also"></a>См. также  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)