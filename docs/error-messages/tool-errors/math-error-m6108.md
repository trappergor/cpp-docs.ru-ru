---
title: Математическая ошибка M6108 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfeca48aa04ebfbc097649e5c25253166c50dad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6108"></a>Математическая ошибка M6108
квадратный корень  
  
 Операнд в операции квадратный корень было отрицательным.  
  
 Программа завершается с кодом выхода 136.  
  
> [!NOTE]
>  `sqrt` Функции в библиотеке времени выполнения C и встроенная функция FORTRAN **SQRT** не создают эту ошибку. C `sqrt` функция проверяет аргумент перед выполнением операции и возвращает значение ошибки, если операнд является отрицательным значением. FORTRAN **SQRT** функции приводит к возникновению ошибки домена [M6201](../../error-messages/tool-errors/math-error-m6201.md) вместо ошибки.