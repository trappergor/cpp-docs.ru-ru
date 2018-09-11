---
title: Последний символ в строке | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c5783fcdb1bccbfe7e2a316fa1ea4285519bb1b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593562"
---
# <a name="last-character-in-a-string"></a>Последний символ в строке
Следуйте приведенным ниже советам:  
  
-   Диапазоны младшего байта перекрывают во многих случаях набор символов ASCII. Можно безопасно использовать безопасность побайтового поиска для управляющие символы (не более 32).  
  
-   Рассмотрим следующую строку кода, который может быть проверка ли последний символ в строке является символом обратной косой черты.  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Так как `strlen` не привязана к MBCS, он возвращает число байтов, не число символов, в многобайтовой строке. Кроме того, обратите внимание, что в некоторых кодовых страниц (например 932), "\\" (0x5c) является допустимым младшим байтом (`sz` является строка C).  
  
     Одно из возможных решений является переписать код таким образом:  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     Этот код использует функциями MBSC `_mbsrchr` и `_mbsinc`. Эти функции не многобайтовую, их можно различать "\\«символ и младший байт»\\". Код выполняет какие-либо действия, если последний символ в строке является значение null («\0»).  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Присваивание символов](../text/character-assignment.md)