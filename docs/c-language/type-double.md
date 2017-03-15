---
title: "Тип double | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "double - тип данных"
  - "мантисса, переменные с плавающей запятой"
  - "переносимость [C++], double - тип"
  - "double - тип"
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Тип double
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Значения типа double с двойной точностью имеют размер 8 байт.  Формат напоминает формат чисел с плавающей запятой, за исключением того, что он имеет 11\-разрядную экспоненту \(ее значение может превышать 1023\) и 52\-разрядную мантиссу, а также еще один старший разряд.  Значения типа double в этом формате могут находиться в диапазоне примерно от 1,7E–308 до 1,7E\+308.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Тип double содержит 64 разряда: 1 для знака, 11 для экспоненты и 52 для мантиссы.  Он имеет диапазон \+\/–1,7E308 с точностью не менее 15 знаков.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)