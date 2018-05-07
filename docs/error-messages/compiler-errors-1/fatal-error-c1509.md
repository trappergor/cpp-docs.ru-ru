---
title: Неустранимая ошибка C1509 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fec83f6b6138eacc613e560b9da4557079d6677d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1509"></a>Неустранимая ошибка C1509
ограничение компилятора: слишком много состояний обработчика исключений в функции «функция». Упростите функцию  
  
 Код превысил внутреннее ограничение состояний обработчика исключений (32 768 состояний).  
  
 Наиболее распространенной причиной является то, что функция содержит сложное выражение определенных пользователем переменных класса и арифметические операторы.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Упростите выражения с помощью назначения общих подвыражений временные переменные.  
  
2.  Разбейте функцию на более мелкие функции.