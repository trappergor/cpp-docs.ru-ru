---
title: Обозначение компонентов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d807087be171a2ad63ed37a8b359c3200c812040
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="filename-parts-syntax"></a>Обозначение компонентов имени файла
Обозначение компонентов имени файла в командах представляет компоненты первого зависимого имени файла (который может быть подразумеваемой). Компонентов имени файла являются диск файла, путь, базовое имя и расширение — указанное, не как она существует на диске. Используйте **%s** для представления полного имени файла. Используйте **%&#124;**[*частей*]**F** (вертикальная черта символ после знака процентов) для представления компонентов имени файла, где *частей*может содержать ноль или несколько букв в любом порядке.  
  
|Буква|Описание|  
|------------|-----------------|  
|Без буквы|Полное имя (то же, что **%s**)|  
|**d**|Диск|  
|**p**|Путь|  
|**f**|Базовое имя файла|  
|**e**|Расширение файла|  
  
 Например, если имя файла c:\prog.exe:  
  
-   %s будет c:\prog.exe  
  
-   %&#124;F будет c:\prog.exe  
  
-   %&#124;dF будет c  
  
-   %&#124;pF будет c:\  
  
-   %&#124;fF будет prog  
  
-   %&#124;eF будет exe-файла  
  
## <a name="see-also"></a>См. также  
 [Команды в файле Makefile](../build/commands-in-a-makefile.md)