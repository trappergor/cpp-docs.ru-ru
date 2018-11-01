---
title: Выражения в предобработке файлов makefile
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: 8d7b8cd489eabf239cbc993181142ca84431cd82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594874"
---
# <a name="expressions-in-makefile-preprocessing"></a>Выражения в предобработке файлов makefile

**! Если** или **! ELSE IF** `constantexpression` состоит из целочисленных констант (в нотации десятичное или языка C), строковых констант или команд. Используйте скобки для группирования выражений. Выражения используют стиле длинное целое число со знаком арифметические; числа являются в виде 32-разрядных дополнительном в диапазоне от-2147483648 до 2147483647.

Выражения могут использовать операторы, выполняющие действия с константными значениями, кодами завершения команд, строки, макросы и путями файловой системы.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Операторы предварительной обработки файлов makefile](../build/makefile-preprocessing-operators.md)

[Выполнение программ в ходе предварительной обработки](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>См. также

[Предварительная обработка файла Makefile](../build/makefile-preprocessing.md)