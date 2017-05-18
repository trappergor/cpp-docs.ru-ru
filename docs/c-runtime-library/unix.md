---
title: "UNIX | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unix
dev_langs:
- C++
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 7
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 10c834b166ccc055ae8e43b2f2851566c6165d29
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="unix"></a>UNIX
Если планируется переносить программы в среду UNIX, придерживайтесь следующих правил:  
  
-   Не удаляйте файлы заголовков из подкаталога SYS. Файлы заголовков SYS можно размещать в другом месте только в том случае, если не планируется переносить программы в UNIX.  
  
-   Используйте UNIX-совместимый разделитель пути в подпрограммах, принимающие в качестве аргументов строки, представляющие пути и имена файлов. UNIX для этих целей поддерживает только косую черту (/), тогда как операционные системы Win32 поддерживают и обратную косую черту (\\), и косую черту (/). Таким образом, в данной документации (например, в операторах `#include`) в качестве разделителей пути используются UNIX-совместимые косые черты. (Однако командная оболочка операционной системы Windows, CMD.EXE, не поддерживает косую черту в командах, вводимых в командной строке.)  
  
-   Используйте пути и имена файлов, правильно работающие в UNIX, где в них учитывается регистр. Файловая система FAT в операционных системах Win32 не учитывает регистр; файловая система NTFS сохраняет регистр для списков каталогов, но не учитывает регистр при поиске файлов и в других системных операциях.  
  
    > [!NOTE]
    >  В этой версии Visual C++ информация о совместимости с UNIX была удалена из описаний функций.  
  
## <a name="see-also"></a>См. также  
 [Совместимость](../c-runtime-library/compatibility.md)
