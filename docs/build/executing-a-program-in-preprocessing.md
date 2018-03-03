---
title: "Выполнение программ в предварительной обработке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef000f6611c9cb3794da8e46e6b905e57d5ecf92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="executing-a-program-in-preprocessing"></a>Выполнение программ в ходе предварительной обработки
Чтобы использовать код выхода команды во время предварительной обработки, укажите команду, с любыми аргументами в квадратные скобки ([]). Все макросы расширяются до выполнения команды. NMAKE замещает определение команды с кодом выхода команды, который можно использовать в выражении для управления предварительной обработки.  
  
## <a name="see-also"></a>См. также  
 [Выражения в предобработке файлов Makefile](../build/expressions-in-makefile-preprocessing.md)