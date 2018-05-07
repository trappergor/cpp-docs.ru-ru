---
title: Varargs | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7b71cd426bc89570f9d394f3e38dc7a002f6e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="varargs"></a>Функции с переменным количеством аргументов (Varargs)
Если параметры передаются через varargs (например, кнопку с многоточием аргументов), по существу обычная передача параметра применяется, включая вытеснение пятого и последующих аргументов. Снова становится вызываемый отвечает за дамп аргументов, которые получают свой адрес. С плавающей запятой только для значений целое число и регистр с плавающей запятой будет содержать значение с плавающей запятой в случае, если вызываемый ожидает значение в целочисленные регистры.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)