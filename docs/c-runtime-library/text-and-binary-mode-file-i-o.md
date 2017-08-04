---
title: "Файловый ввод-вывод в текстовом и двоичном режиме | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- files [C++], open functions
- I/O [CRT], text files
- functions [CRT], file access
- binary access, binary mode file I/O
- translation, modes
- I/O [CRT], binary
- text files, I/O
- I/O [CRT], translation modes
- translation modes (file I/O)
- binary access
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: 10
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a788242344c7cb3b89765e7476fdd23dbf68982d
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="text-and-binary-mode-file-io"></a>Файловый ввод-вывод в текстовом и двоичном режиме
Операции файлового ввода-вывода выполняются в одном из двух режимов преобразования, текстовом или двоичном, в зависимости от режима, в котором этот файл открыт. Файлы данных обычно обрабатываются в текстовом режиме. Для управления режимом преобразования файла можно:  
  
-   Сохранить текущий параметр по умолчанию и указывать альтернативный режим только при открытии выбранных файлов.  
  
-   С помощью функции [_set_fmode](../c-runtime-library/reference/set-fmode.md) изменить режим по умолчанию для вновь открываемых файлов. С помощью функции [_get_fmode](../c-runtime-library/reference/get-fmode.md) определить текущий режим по умолчанию. Начальная настройка по умолчанию — текстовый режим (`_O_TEXT`).  
  
-   Изменить режим преобразования по умолчанию напрямую, определив в программе глобальную переменную [_fmode](../c-runtime-library/fmode.md). Значение этой переменной устанавливается функцией `_set_fmode`, но его можно также задать непосредственно.  
  
 При вызове функции, открывающей файл, например [_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) или [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), можно переопределить текущее значение по умолчанию для параметра `_fmode`, передав соответствующий аргумент в функцию [_set_fmode](../c-runtime-library/reference/set-fmode.md). Потоки `stdin`, `stdout` и `stderr` по умолчанию всегда открываются в текстовом режиме; можно также переопределить это значение по умолчанию при открытии любого из этих файлов. После открытия файла режим преобразования можно изменить с помощью функции [_setmode](../c-runtime-library/reference/setmode.md), передав ей дескриптора файла.  
  
## <a name="see-also"></a>См. также  
 [Ввод и вывод](../c-runtime-library/input-and-output.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
