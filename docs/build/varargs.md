---
title: "Varargs | Документы Microsoft"
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
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3d22a5c3f20480d1e904ec8e087114385ba7ee9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="varargs"></a>Функции с переменным количеством аргументов (Varargs)
Если параметры передаются через varargs (например, кнопку с многоточием аргументов), по существу обычная передача параметра применяется, включая вытеснение пятого и последующих аргументов. Снова становится вызываемый отвечает за дамп аргументов, которые получают свой адрес. С плавающей запятой только для значений целое число и регистр с плавающей запятой будет содержать значение с плавающей запятой в случае, если вызываемый ожидает значение в целочисленные регистры.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)