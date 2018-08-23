---
title: И подставляемый ассемблерный код | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff2b99eedcdd81a96dc3091046a4f62ffe002509
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42573169"
---
# <a name="intrinsics-and-inline-assembly"></a>Внутренний и подставляемый ассемблерный код
Одно из ограничений для x64 компилятора желательно использовать не поддерживает встроенный ассемблер. Это означает, что функции, не может быть написаны на C или C++, должны записываться в виде подпрограмм или встроенных функций, поддерживаемых компилятором. Некоторые функции, чувствительны к производительности, а другие нет. Функции, чувствительные к производительности должны быть реализованы как встроенные функции.  
  
 Компилятор поддерживает встроенные функции описаны в [встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)