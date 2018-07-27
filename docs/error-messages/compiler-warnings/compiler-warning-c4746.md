---
title: C4746 Предупреждение компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d00c75b2b7cdf2fdafb4e109496a701fb561cb9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270902"
---
# <a name="compiler-warning-c4746"></a>C4746 Предупреждение компилятора
переменное обращение "\<выражение >" является параметром/volatile: [iso&#124;ms]; попробуйте использовать встроенные функции __iso_volatile_load/store.  
  
 C4746 создается каждый раз, когда переменная с модификатором volatile осуществляется напрямую. Он предназначен для выявления кода расположений, которые зависят от конкретной модели volatile указанной в настоящее время (который можно управлять при помощи [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора). В частности может быть полезно для выявления барьеры памяти оборудования, созданный компилятором, если используется /volatile:ms.  
  
 Встроенные функции __iso_volatile_load/store используется для прямого обращения к энергонезависимой памяти без влияния volatile модели. С помощью этих встроенных функций не будет вызывать C4746.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .