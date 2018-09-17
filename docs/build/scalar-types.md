---
title: Скалярные типы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ad0fa75380ca971f7ac2dfa4c370c076f7d552e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700964"
---
# <a name="scalar-types"></a>Скалярные типы

Несмотря на то, что доступ к данным может быть обусловлено любой выравнивание, рекомендуется выравнивание данных в исходном во избежание потери производительности (или диапазоне). Перечисления являются целочисленных констант и обрабатываются как 32-разрядных целых чисел. В следующей таблице описаны определения типа и рекомендуемые хранилища для него, как в случае выравнивания, с помощью следующих значений:

- Byte - 8 бит

- Word - 16 бит

- Двойное слово — 32 бита

- Четыре слова - 64 бита

- Word являются восьмеричным - 128 бит

|||||
|-|-|-|-|
|Скалярный тип|Тип данных C|Размер хранилища (в байтах)|Рекомендуемое выравнивание|
|**INT8**|**char**|1|Byte|
|**UINT8**|**unsigned char**|1|Byte|
|**INT16**|**short**|2|Слово|
|**UINT16**|**unsigned short**|2|Слово|
|**INT32**|**int**, **long**|4|Двойное|
|**UINT32**|**целое число без знака, long без знака**|4|Двойное|
|**INT64**|**__int64**|8|Quadword|
|**UINT64**|**unsigned __int64**|8|Quadword|
|**FP32 (одинарная точность)**|**float**|4|Двойное|
|**FP64 (двойная точность)**|**double**|8|Quadword|
|**УКАЗАТЕЛЬ**|<strong>\*</strong>|8|Quadword|
|**__m64**|**__m64 структуры**|8|Quadword|
|**__m128**|**__m128 структуры**|16|Octaword|

## <a name="see-also"></a>См. также

[Типы и хранилище](../build/types-and-storage.md)