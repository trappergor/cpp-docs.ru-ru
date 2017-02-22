---
title: "Присваивание символов | Microsoft Docs"
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
  - "знаки [C++], назначения"
  - "MBCS [C++], присваивание символов"
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Присваивание символов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Рассмотрим следующий пример, в котором цикл `while` проверяет строку, копируя все символы, кроме "X", в другую строку.  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Код копирует байт из `sz2` в положение, указанное в `sz1`, а затем увеличивает `sz1`, чтобы получить следующий байт.  Однако, если следующий символ в `sz2` состоит из двух байтов, в положение, указанное в `sz1`, копируется только первый байт.  В следующем коде для безопасного копирования символа используется переносимая функция, а для правильного увеличения `sz1` и `sz2` — другая переносимая функция.  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## См. также  
 [Советы по программированию многобайтовой кодировки](../Topic/MBCS%20Programming%20Tips.md)   
 [Сравнение знаков](../text/character-comparison.md)