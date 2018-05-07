---
title: Ошибка вычислителя выражений CXX0016 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0016
dev_langs:
- C++
helpviewer_keywords:
- CAN0016
- CXX0016
ms.assetid: af94a2ae-e835-4da6-8d2f-5c879f72eda2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cace3caf930c2b51bb1306b02bb7126373ddfe74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0016"></a>Ошибка вычислителя выражений CXX0016
слишком большая константа  
  
 Вычислитель выражений C не может принимать константу целое число без знака размером более 4 294 967 295 (0FFFFFFFF в шестнадцатеричной записи), или константы с плавающей запятой, величина которого больше, чем 1.8E + 308.  
  
 Эта ошибка идентична ошибке CAN0016.