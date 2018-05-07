---
title: Ошибка вычислителя выражений CXX0065 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78c25c9c6bde27219f10e4047dc7a6ab416f55d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0065"></a>Ошибка вычислителя выражений CXX0065
переменной требуется фрейм стека  
  
 Выражение содержит переменную, которая существует в текущей области, но еще не создана.  
  
 Эта ошибка может произойти, если вы выполнили шаг с заходом в прологе функции, но еще не набор кадр стека для функции, или если вы выполнили шаг с заходом в код выхода для функции.  
  
 Пошаговое выполнение кода пролога, пока не была настроена кадр стека перед вычислением выражения.  
  
 Эта ошибка идентична ошибке CAN0065.