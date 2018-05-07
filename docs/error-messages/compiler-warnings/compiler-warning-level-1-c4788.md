---
title: Предупреждение компилятора (уровень 1) C4788 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a43fb9d79c63637b2bff9a27661a9f848ef6dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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