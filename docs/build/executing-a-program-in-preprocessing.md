---
title: Выполнение программ в ходе предварительной обработки
ms.date: 11/04/2016
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
ms.openlocfilehash: d95079349981b073533bb00abcd053454542a044
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413307"
---
# <a name="executing-a-program-in-preprocessing"></a>Выполнение программ в ходе предварительной обработки

Чтобы использовать код выхода команды во время предварительной обработки, укажите команду, с любыми аргументами в квадратные скобки ([]). Все макросы расширяются до выполнения команды. NMAKE заменяет определение команды код выхода команды, который может использоваться в выражении для управления предварительной обработки.

## <a name="see-also"></a>См. также

[Выражения в предобработке файлов Makefile](../build/expressions-in-makefile-preprocessing.md)
