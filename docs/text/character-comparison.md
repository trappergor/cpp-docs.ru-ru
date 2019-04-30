---
title: Сравнение знаков
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 075a22634f254c2ea634a1171ee157971fe5918e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410698"
---
# <a name="character-comparison"></a>Сравнение знаков

Следуйте приведенным ниже советам:

- Сравнение известный старший байт со знаком ASCII работает правильно:

    ```cpp
    if( *sz1 == 'A' )
    ```

- Сравнение двух неизвестных символов необходимо использовать один из макросов, определенных в файле Mbstring.h:

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   Это гарантирует, что оба байт двухбайтовой сравниваются на предмет равенства.

## <a name="see-also"></a>См. также

[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)<br/>
[Переполнение буфера](../text/buffer-overflow.md)
