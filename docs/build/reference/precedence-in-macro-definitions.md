---
title: Приоритет в макроопределениях
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 38a653a9f460beae81f9f88ea457870d30f25339
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826643"
---
# <a name="precedence-in-macro-definitions"></a>Приоритет в макроопределениях

Если макрос имеет несколько определений, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Макрос, определенный в командной строке

1. Макрос, определенный в файле makefile или включить файл

1. Унаследованные макрос переменной среды

1. Макрос, определенный в файле Tools.ini

1. Предопределенный макрос, такие как [CC](command-macros-and-options-macros.md) и [AS](command-macros-and-options-macros.md)

Используйте /E для макросы, унаследованные из переменных среды для переопределения макросы makefile с тем же именем. Используйте **! UNDEF** для переопределения командной строки.

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](defining-an-nmake-macro.md)
