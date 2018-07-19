---
title: Выполнение программ в предварительной обработке | Документы Microsoft
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
ms.openlocfilehash: da87a87a2e97736d202b7ddb9be2dbec54fed44d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367203"
---
# <a name="executing-a-program-in-preprocessing"></a>Выполнение программ в ходе предварительной обработки
Чтобы использовать код выхода команды во время предварительной обработки, укажите команду, с любыми аргументами в квадратные скобки ([]). Все макросы расширяются до выполнения команды. NMAKE замещает определение команды с кодом выхода команды, который можно использовать в выражении для управления предварительной обработки.  
  
## <a name="see-also"></a>См. также  
 [Выражения в предобработке файлов Makefile](../build/expressions-in-makefile-preprocessing.md)