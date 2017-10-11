---
title: "C4746 Предупреждение компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1b88f51aa9365c0795c8d3d944ba9f3a8db059d9
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4746"></a>C4746 Предупреждение компилятора
переменное обращение "\<выражение >" является параметром/volatile: [iso &#124; ms]; попробуйте использовать встроенные функции __iso_volatile_load/store.  
  
 C4746 создается каждый раз, когда переменная с модификатором volatile осуществляется напрямую. Он предназначен для выявления кода расположений, которые зависят от конкретной модели volatile указанной в настоящее время (который можно управлять при помощи [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора). В частности может быть полезно для выявления барьеры памяти оборудования, созданный компилятором, если используется /volatile:ms.  
  
 Встроенные функции __iso_volatile_load/store используется для прямого обращения к энергонезависимой памяти без влияния volatile модели. С помощью этих встроенных функций не будет вызывать C4746.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .
