---
title: Сравнение знаков
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 206910d4b76f93a92ee5230a227d6f0346a85e61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615414"
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