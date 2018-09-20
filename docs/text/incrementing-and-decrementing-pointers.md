---
title: Увеличение и уменьшение значений указателей | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e220c138ebcbb9010aef78931b07c2b04b095ea7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447669"
---
# <a name="incrementing-and-decrementing-pointers"></a>Увеличение и уменьшение значений указателей

Следуйте приведенным ниже советам:

- Укажите старшие байты, а не младшие байты. Обычно небезопасна указатель к младшим байтом. Обычно лучше проверять строку вперед, а не в обратном порядке.

- Существует указатель увеличить или уменьшить значение функции и макросы, которые перемещают на целый знак:

    ```cpp
    sz1++;
    ```

   принимает следующий вид:

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc` И `_mbsdec` функции правильно увеличения и уменьшения в `character` единиц, независимо от размера символа.

- Для уменьшения, что требуется указатель на начало строки, как показано ниже:

    ```cpp
    sz2--;
    ```

   принимает следующий вид:

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   Кроме того, может быть указатель головной допустимому символу в строке, таким образом, чтобы:

    ```cpp
    sz2Head < sz2
    ```

   Необходимо иметь указатель на допустимый старший байт.

- Вы можете использовать указатель к предыдущему символу ускорить последующие вызовы `_mbsdec`.

## <a name="see-also"></a>См. также

[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)<br/>
[Индексы байтов](../text/byte-indices.md)