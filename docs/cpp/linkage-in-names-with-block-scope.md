---
title: "Компоновка в именах в области блока | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "область действия блока [C++]"
  - "внешняя компоновка, правила связи областей"
  - "компоновка [C++], правила связи областей"
  - "имена [C++], правила связи областей"
  - "область [C++], правила связи"
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Компоновка в именах в области блока
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие правила компоновки применяются к именам с областью видимости "блок" \(локальные имена\).  
  
-   Имена, объявленные как `extern`, имеют внешние ссылки. Исключение составляют случаи, когда они ранее были объявлены как **статические**.  
  
-   Все остальные имена с областью видимости "блок" не имеют компоновки.  
  
## См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)