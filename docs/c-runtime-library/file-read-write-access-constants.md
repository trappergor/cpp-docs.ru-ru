---
title: "Константы доступа чтения и записи файлов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.constants.file
dev_langs: C++
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 789d0ae6b0b9b38312896adf079e7c10dcde7556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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