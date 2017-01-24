---
title: "Тип char | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "char - ключевое слово [C]"
  - "тип char"
  - "unsigned char - ключевое слово [C]"
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Тип char
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип `char` используется для хранения целочисленного значения члена представительной кодировки.  Целочисленное значение — это код ASCII, соответствующий указанному символу.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Значения символов типа `unsigned char` находятся в диапазоне от 0 до 0xFF по шестнадцатеричной системе счисления.  **signed char** имеет диапазон от 0x80 до 0x7F.  Эти диапазоны преобразуются в диапазоны от 0 до 255 и от \-128 до \+127 по десятичной системе счисления соответственно.  Параметр компилятора \/J меняет используемый по умолчанию вариант: вместо **signed** устанавливается `unsigned`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)