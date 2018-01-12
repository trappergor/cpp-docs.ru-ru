---
title: "Предупреждение компилятора (уровень 1) C4788 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4788
dev_langs: C++
helpviewer_keywords: C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6f876dada851f46b7708ef1b34da4bae6f96dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4788"></a>Предупреждение компилятора (уровень 1) C4788
«Идентификатор»: идентификатор усечен до «число» знаков  
  
 Компилятор ограничивает максимальную длину для имени функции. Когда компилятор создает фанклеты для кода EH/SEH, он формирует имя funclet путем добавления к имени функции некоторый текст, например «__catch,» «\__unwind», или другой строки.  
  
 Результирующее имя funclet может быть слишком много времени, и компилятор его и создает предупреждение C4788.  
  
 Чтобы устранить это предупреждение, сократите имя исходной функции. Если функция является функцией шаблона C++ или метода, используйте определение типа для части имени. Пример:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 можно заменить:  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Это предупреждение возникает только в [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] компилятора.