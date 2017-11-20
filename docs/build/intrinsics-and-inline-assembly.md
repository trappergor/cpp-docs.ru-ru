---
title: "Внутренний и подставляемый ассемблерный | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c60932b719b25365c7d8f65a4649ef782a4f9888
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="intrinsics-and-inline-assembly"></a>Внутренний и подставляемый ассемблерный код
Одно из ограничений для [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] компилятор будет для них не поддерживается встроенный ассемблер. Это означает, что функции, не может быть написаны на C или C++, должны быть написаны как подпрограмм или внутренних функций, поддерживаемых компилятором. Некоторые функции являются чувствительны к производительности, а другие — нет. Функции, чувствительные к производительности должны быть реализованы как встроенные функции.  
  
 Компилятор поддерживает встроенные функции описаны в [встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)