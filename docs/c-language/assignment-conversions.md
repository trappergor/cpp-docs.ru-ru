---
title: "Преобразования назначений | Microsoft Docs"
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
  - "преобразования присваиваний"
  - "преобразования, присвоение"
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Преобразования назначений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В операциях присваивания тип присваиваемого значения преобразуется в тип переменной, которой присваивается значение.  C позволяет при присваивании выполнять преобразования между целочисленными типами и типами с плавающей запятой даже в случае потери данных при преобразовании.  Используемый метод преобразования зависит от типов, участвующих в операции присваивания, как описано в разделе [Обычные арифметические преобразования](../c-language/usual-arithmetic-conversions.md) и в следующих разделах:  
  
-   [Преобразования из целочисленных типов со знаком](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Преобразования из целочисленных типов без знака](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Преобразования из типов с плавающей запятой](../Topic/Conversions%20from%20Floating-Point%20Types.md)  
  
-   [Преобразования в типы указателей и из типов указателей](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Преобразования из других типов](../c-language/conversions-from-other-types.md)  
  
 Квалификаторы типа не влияют на допустимость преобразования, хотя в левой части операции присваивания невозможно использовать L\-значение **const**.  
  
## См. также  
 [Преобразования типов](../c-language/type-conversions-c.md)