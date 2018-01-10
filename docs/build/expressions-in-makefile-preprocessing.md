---
title: "Выражения в предобработке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7bea4f0c4fea2c2d04681674734bc989424c7951
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-makefile-preprocessing"></a>Выражения в предобработке файлов makefile
**! Если** или **! ELSE IF** `constantexpression` состоит из целочисленных констант (в десятичной нотации или языка C нотации), строковых констант или команд. Используйте круглые скобки для группирования выражений. Выражения используют C-стиле длинное целое число со знаком арифметические; числа являются в виде 32-разрядных дополнительном в диапазоне от-2147483648 до 2147483647.  
  
 Выражения могут использовать операторы, выполняющие действия с константными значениями, кодами завершения команд, строки, макросами и путями файловой системы.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Операторы предварительной обработки файлов makefile](../build/makefile-preprocessing-operators.md)  
  
 [Выполнение программ в ходе предварительной обработки](../build/executing-a-program-in-preprocessing.md)  
  
## <a name="see-also"></a>См. также  
 [Предварительная обработка файла Makefile](../build/makefile-preprocessing.md)