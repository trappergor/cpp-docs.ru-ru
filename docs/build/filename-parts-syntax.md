---
title: "Обозначение компонентов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a481f8c461cb4fddd4acb090edb2f2b5fd18636d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="filename-parts-syntax"></a>Обозначение компонентов имени файла
Обозначение компонентов имени файла в командах представляет компоненты первого зависимого имени файла (который может быть подразумеваемой). Компонентов имени файла являются диск файла, путь, базовое имя и расширение — указанное, не как она существует на диске. Используйте **%s** для представления полного имени файла. Используйте **% &#124;** [*частей*]**F** (вертикальная черта символ после знака процентов) для представления компонентов имени файла, где *частей* может содержать ноль или несколько букв в любом порядке.  
  
|Буква|Описание:|  
|------------|-----------------|  
|Без буквы|Полное имя (то же, что **%s**)|  
|**d**|Диск|  
|**p**|Путь|  
|**f**|Базовое имя файла|  
|**e**|Расширение файла|  
  
 Например, если имя файла c:\prog.exe:  
  
-   %s будет c:\prog.exe  
  
-   % &#124; F будет c:\prog.exe  
  
-   % &#124; будет dF c  
  
-   % &#124; будет pF c:\  
  
-   % &#124; будет fF prog  
  
-   % &#124; eF может быть exe-файла  
  
## <a name="see-also"></a>См. также  
 [Команды в файле Makefile](../build/commands-in-a-makefile.md)