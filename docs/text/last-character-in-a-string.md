---
title: "Последний знак в строке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b766bec977f35f9f346723cbaf3f62e48c8c878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="last-character-in-a-string"></a>Последний символ в строке
Используйте следующие рекомендации:  
  
-   Диапазоны младшего байта перекрывают во многих случаях набор символов ASCII. Можно безопасно использовать безопасность побайтового поиска для управляющие символы (не более 32).  
  
-   Рассмотрим следующую строку кода, который может быть проверка на наличие последним символом в строке является символом обратной косой черты.  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Поскольку `strlen` не привязана к MBCS, он возвращает количество байтов, а не количество символов, в многобайтовой строке. Кроме того, обратите внимание, что в некоторых кодовых страниц (например 932) "\\" (0x5c) является допустимым младшим байтом (`sz` является строка C).  
  
     Одно из возможных решений является код написан таким образом:  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     Этот код использует функции многобайтовой Кодировки `_mbsrchr` и `_mbsinc`. Поскольку эти функции поддерживают многобайтовую, их можно отличить "\\«символов и младший байт»\\". Код выполняет какие-либо действия, если последним символом в строке является значение null («\0»).  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Присваивание символов](../text/character-assignment.md)