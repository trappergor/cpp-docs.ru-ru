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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f92bae0e75d9a09de874cd999c044e703b3f3171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4746"></a>C4746 Предупреждение компилятора
переменное обращение "\<выражение >" является параметром/volatile: [iso &#124; ms]; попробуйте использовать встроенные функции __iso_volatile_load/store.  
  
 C4746 создается каждый раз, когда переменная с модификатором volatile осуществляется напрямую. Он предназначен для выявления кода расположений, которые зависят от конкретной модели volatile указанной в настоящее время (который можно управлять при помощи [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора). В частности может быть полезно для выявления барьеры памяти оборудования, созданный компилятором, если используется /volatile:ms.  
  
 Встроенные функции __iso_volatile_load/store используется для прямого обращения к энергонезависимой памяти без влияния volatile модели. С помощью этих встроенных функций не будет вызывать C4746.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .