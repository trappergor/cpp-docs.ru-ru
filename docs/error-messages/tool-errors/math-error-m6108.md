---
title: "Математическая ошибка M6108 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6db123d9cb96274848a3edd9f845f86f413d8e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6108"></a>Математическая ошибка M6108
квадратный корень  
  
 Операнд в операции квадратный корень было отрицательным.  
  
 Программа завершается с кодом выхода 136.  
  
> [!NOTE]
>  `sqrt` Функции в библиотеке времени выполнения C и встроенная функция FORTRAN **SQRT** не создают эту ошибку. C `sqrt` функция проверяет аргумент перед выполнением операции и возвращает значение ошибки, если операнд является отрицательным значением. FORTRAN **SQRT** функции приводит к возникновению ошибки домена [M6201](../../error-messages/tool-errors/math-error-m6201.md) вместо ошибки.