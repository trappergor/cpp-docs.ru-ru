---
title: "Целевые объекты | Microsoft Docs"
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
helpviewer_keywords: 
  - "целевые объекты, определение (NMAKE)"
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Целевые объекты
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В строке зависимости можно определить один или несколько целевых объектов с использование любого допустимого имени файла, каталога или [псевдоцелевого объекта](../build/pseudotargets.md).  Для разделения целевых объектов используйте один или несколько пробелов или знаков табуляции.  Регистр знаков в именах целевых объектов не учитывается.  Разрешено указание путей с именами файлов.  Длина имени целевого объекта не должна превышать 256 знаков.  Если имя целевого объекта, за которым следует двоеточие, состоит из одного знака, следует использовать разделяющий пробел. В противном случае программа NMAKE интерпретирует это сочетание знаков как спецификатор диска.  
  
## Дополнительные сведения  
 [Псевдоцелевые объекты](../build/pseudotargets.md)  
  
 [Несколько целевых объектов](../build/multiple-targets.md)  
  
 [Кумулятивные зависимости](../build/cumulative-dependencies.md)  
  
 [Целевые объекты в нескольких блоках описания](../build/targets-in-multiple-description-blocks.md)  
  
 [Побочные эффекты зависимостей](../build/dependency-side-effects.md)  
  
## См. также  
 [Блоки описания](../build/description-blocks.md)