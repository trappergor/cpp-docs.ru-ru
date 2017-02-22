---
title: "Неустранимая ошибка C1509 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1509"
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка C1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: слишком много состояний обработчика исключений в функции «функция». упростите функцию  
  
 Код превысил внутреннее ограничение состояний обработчика исключений \(32 768 состояний\).  
  
 Наиболее общей причиной является то, что функция содержит сложное выражение определенных пользователем переменных класса и арифметические операторы.  
  
### Возможные способы устранения данной ошибки  
  
1.  Упростите выражения с помощью назначения общих подвыражений временным переменным.  
  
2.  Разделите функцию на более малые функции.