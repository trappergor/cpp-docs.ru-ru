---
title: "Ошибка средств компоновщика LNK1000 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1000"
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка средств компоновщика LNK1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неизвестная ошибка; о возможностях технической поддержки см. в документации  
  
 Соберите сведения об обстоятельствах появления ошибки, попытайтесь изолировать данную проблему и создать воспроизводимый тестовый случай, а затем обратитесь в `Microsoft Product Support Services`.  Сведения о выявлении ошибок и отправке отчетов см. в разделе [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Эта ошибка может появиться при объединении файлов стандартных заголовков \(например, dos.h\) с собственными файлами разработчика.  В директиве `#include` необходимо сначала указывать стандартные заголовки, за которыми будут следовать собственные файлы заголовков.