---
title: Последний знак в строке | Документы Microsoft
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88cde1d2eb30103462f7ae8f8c06274a2977fc36
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855647"
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