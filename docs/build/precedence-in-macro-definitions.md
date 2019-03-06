---
title: Приоритет в макроопределениях
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 7f847cd7cea736ff9b4360a050767d00bd6cf539
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421510"
---
# <a name="precedence-in-macro-definitions"></a>Приоритет в макроопределениях

Если макрос имеет несколько определений, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Макрос, определенный в командной строке

1. Макрос, определенный в файле makefile или включить файл

1. Унаследованные макрос переменной среды

1. Макрос, определенный в файле Tools.ini

1. Предопределенный макрос, такие как [CC](../build/command-macros-and-options-macros.md) и [AS](../build/command-macros-and-options-macros.md)

Используйте /E для макросы, унаследованные из переменных среды для переопределения макросы makefile с тем же именем. Используйте **! UNDEF** для переопределения командной строки.

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](../build/defining-an-nmake-macro.md)
