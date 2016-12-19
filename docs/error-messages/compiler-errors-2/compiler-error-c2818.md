---
title: "Ошибка компилятора C2818 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2818"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2818"
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2818
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

приложение перегруженный оператор «\-\>' рекурсивн через тип «тип»  
  
 В переопределении оператора доступа для члена класса содержится рекурсивный оператор `return`.  Чтобы переопределить рекурсивный оператор `->`, переместите рекурсивную подпрограмму в отдельную функцию, которая вызывается из переопределяющей функции оператора.