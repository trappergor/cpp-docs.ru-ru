---
title: "Проверка на наличие ошибок извлечения | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ошибки извлечения"
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Проверка на наличие ошибок извлечения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функции обработки ошибок вывода, описанные в [Функции обработки ошибок](../standard-library/output-file-stream-member-functions.md), применяются к входным потоки.  Проверка ошибок во время извлечения важен.  Рассмотрим эту оператора:  
  
```  
cin >> n;  
```  
  
 Если `n` знаковое целое число, значение больше 32,767, то \(максимальное допустимое значение или MAX\_INT\) устанавливает бит `fail` потока, а объект `cin` будут неиспользованными.  Все последующие извлечения выдаются в текущем возврате без значения сохраненной.  
  
## См. также  
 [Потоки ввода](../standard-library/input-streams.md)