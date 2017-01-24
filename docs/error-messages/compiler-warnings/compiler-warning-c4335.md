---
title: "Предупреждение компилятора C4335 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4335"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4335"
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4335
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обнаружен файловый формат Mac: преобразуйте исходный файл в формат DOS или UNIX  
  
 Символ окончания строки в первой строке исходного файла — "\\r" \(используется в системах Macintosh\), в отличие от UNIX \("\\n"\) или DOS \("\\r\\n"\).  
  
 Это предупреждение выводится всегда в качестве ошибки.  Дополнительные сведения об устранении этого предупреждения см. в разделе [warning](../../preprocessor/warning.md).  Кроме того, это предупреждение возникает только один раз для каждого объекта компиляции.  Поэтому если используется несколько директив `#include`, в которых файлы указываются в формате Macintosh, предупреждение C4335 выдается всего один раз.  
  
 Чтобы создать файлы в формате Macintosh, необходимо использовать **Дополнительные параметры сохранения** \(меню **Файл**\) в Visual Studio.  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C4335.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```