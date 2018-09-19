---
title: Выражения в предобработке | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1070eb01802bd4b39f62ae24519ad6dabca7eb90
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719011"
---
# <a name="expressions-in-makefile-preprocessing"></a>Выражения в предобработке файлов makefile

**! Если** или **! ELSE IF** `constantexpression` состоит из целочисленных констант (в нотации десятичное или языка C), строковых констант или команд. Используйте скобки для группирования выражений. Выражения используют стиле длинное целое число со знаком арифметические; числа являются в виде 32-разрядных дополнительном в диапазоне от-2147483648 до 2147483647.

Выражения могут использовать операторы, выполняющие действия с константными значениями, кодами завершения команд, строки, макросы и путями файловой системы.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Операторы предварительной обработки файлов makefile](../build/makefile-preprocessing-operators.md)

[Выполнение программ в ходе предварительной обработки](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>См. также

[Предварительная обработка файла Makefile](../build/makefile-preprocessing.md)