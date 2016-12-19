---
title: "Функции с переменным количеством аргументов (Varargs) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Функции с переменным количеством аргументов (Varargs)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если параметры передаются с помощью функции varargs \(например, аргументы, задаваемые многоточием\), то фактически применяется обычная передача параметра, включая вытеснение пятого и последующих аргументов.  Кроме того, вызываемый отвечает за дамп аргументов, которые получают свой адрес.  Только для значений с плавающей запятой: целочисленный регистр и регистр с плавающей запятой содержат значение типа float в случае, если вызываемый ожидает значение в целочисленных регистрах.  
  
## См. также  
 [Соглашение о вызовах](../build/calling-convention.md)