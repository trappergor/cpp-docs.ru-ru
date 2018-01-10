---
title: "Неустранимая ошибка C1509 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1509
dev_langs: C++
helpviewer_keywords: C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22cb22ea2186b16fd98d2714779b2475c51d15bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1509"></a>Неустранимая ошибка C1509
ограничение компилятора: слишком много состояний обработчика исключений в функции «функция». Упростите функцию  
  
 Код превысил внутреннее ограничение состояний обработчика исключений (32 768 состояний).  
  
 Наиболее распространенной причиной является то, что функция содержит сложное выражение определенных пользователем переменных класса и арифметические операторы.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Упростите выражения с помощью назначения общих подвыражений временные переменные.  
  
2.  Разбейте функцию на более мелкие функции.