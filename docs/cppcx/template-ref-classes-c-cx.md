---
title: "Классы ссылки шаблонов (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Классы ссылки шаблонов (C++/CX)
Шаблоны C\+\+ не публикуются в метаданных и поэтому не могут иметь быть открытыми или защищенными в программе. Конечно внутри программы можно использовать стандартные шаблоны C\+\+. Кроме того, можно определить закрытый класс ссылки в качестве шаблона и объявить явно специализированный класс ссылки шаблона в качестве закрытого члена открытого класса ссылки.  
  
## Создание шаблонов классов ссылок  
 В следующем примере показано, как объявить закрытый класс ссылки в виде шаблона, как объявить стандартный шаблон C\+\+ и как объявить такие класс и шаблон в качестве членов открытого класса ссылки. Обратите внимание, что стандартный шаблон C\+\+ может быть специализирован типом [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], в данном случае Platform::String^.  
  
 [!code-cpp[cx_templates#01](../snippets/cpp/VS_Snippets_Misc/cx_templates/cpp/class1.h#01)]  
  
## См. также  
 [Система типов \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)