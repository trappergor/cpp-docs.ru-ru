---
title: Внутренний и подставляемый ассемблерный | Документы Microsoft
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
ms.openlocfilehash: 5b8651bea0b1ee9f54ec0af704d92feef0722368
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="intrinsics-and-inline-assembly"></a>Внутренний и подставляемый ассемблерный код
Одно из ограничений для [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] компилятор будет для них не поддерживается встроенный ассемблер. Это означает, что функции, не может быть написаны на C или C++, должны быть написаны как подпрограмм или внутренних функций, поддерживаемых компилятором. Некоторые функции являются чувствительны к производительности, а другие — нет. Функции, чувствительные к производительности должны быть реализованы как встроенные функции.  
  
 Компилятор поддерживает встроенные функции описаны в [встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)