---
title: "Ошибка вычислителя выражений CXX0065 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0065
dev_langs: C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a80869ad54541a493450ce4cc3696da5da6116b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0065"></a>Ошибка вычислителя выражений CXX0065
переменной требуется фрейм стека  
  
 Выражение содержит переменную, которая существует в текущей области, но еще не создана.  
  
 Эта ошибка может произойти, если вы выполнили шаг с заходом в прологе функции, но еще не набор кадр стека для функции, или если вы выполнили шаг с заходом в код выхода для функции.  
  
 Пошаговое выполнение кода пролога, пока не была настроена кадр стека перед вычислением выражения.  
  
 Эта ошибка идентична ошибке CAN0065.