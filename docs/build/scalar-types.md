---
title: "Скалярные типы | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Скалярные типы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Несмотря на то, что обращение к данным возможно при любом выравнивании, в целях повышения производительности рекомендуется использовать выравнивание данных в исходном диапазоне.  Перечисления представляют собой константы целого типа и обрабатываются как 32\-разрядные целые числа.  В следующей таблице приводится определение типа и рекомендуемый для него объем памяти в случае выравнивания с использованием следующих значений:  
  
-   Byte — 8 бит  
  
-   Word — 16 бит  
  
-   Double Word — 32 бит  
  
-   Quad Word — 64 бит  
  
-   Octa Word — 128 бит  
  
|||||  
|-|-|-|-|  
|Скалярный тип|Тип данных C|Объем памяти \(в байтах\)|Рекомендуемое выравнивание|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int, long**|4|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|4|Doubleword|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned \_\_int64**|8|Quadword|  
|**FP32 \(одиночной точности\)**|**float**|4|Doubleword|  
|**FP64 \(двойной точности\)**|**double**|8|Quadword|  
|**POINTER**|**\***|8|Quadword|  
|`__m64`|**struct \_\_m64**|8|Quadword|  
|`__m128`|**struct \_\_m128**|16|Octaword|  
  
## См. также  
 [Типы и хранилище](../build/types-and-storage.md)