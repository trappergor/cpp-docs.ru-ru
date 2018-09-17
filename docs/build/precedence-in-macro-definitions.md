---
title: Приоритет в макроопределениях | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21a3d8873fd1fee61afec865181bab27305bebfd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722219"
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