---
title: Выполнение программ в ходе предварительной обработки
ms.date: 11/04/2016
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
ms.openlocfilehash: a78c9ddc498383d460e617bc26f4e70eb7275eec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577428"
---
# <a name="executing-a-program-in-preprocessing"></a>Выполнение программ в ходе предварительной обработки

Чтобы использовать код выхода команды во время предварительной обработки, укажите команду, с любыми аргументами в квадратные скобки ([]). Все макросы расширяются до выполнения команды. NMAKE заменяет определение команды код выхода команды, который может использоваться в выражении для управления предварительной обработки.

## <a name="see-also"></a>См. также

[Выражения в предобработке файлов Makefile](../build/expressions-in-makefile-preprocessing.md)