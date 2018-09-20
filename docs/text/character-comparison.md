---
title: Сравнение символов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3412939bac9dace6f3abaacda75ed73d6e60f21
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428074"
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