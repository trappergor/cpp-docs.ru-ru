---
title: Выполнение программ в ходе предварительной обработки | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2b0571e67e7c5d24cf31dce6fce548735cad966
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721465"
---
# <a name="executing-a-program-in-preprocessing"></a>Выполнение программ в ходе предварительной обработки

Чтобы использовать код выхода команды во время предварительной обработки, укажите команду, с любыми аргументами в квадратные скобки ([]). Все макросы расширяются до выполнения команды. NMAKE заменяет определение команды код выхода команды, который может использоваться в выражении для управления предварительной обработки.

## <a name="see-also"></a>См. также

[Выражения в предобработке файлов Makefile](../build/expressions-in-makefile-preprocessing.md)