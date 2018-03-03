---
title: "Внутренний и подставляемый ассемблерный | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80eb16eb7fde49c499227bb3d60000e2ac6e5143
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="intrinsics-and-inline-assembly"></a>Внутренний и подставляемый ассемблерный код
Одно из ограничений для [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] компилятор будет для них не поддерживается встроенный ассемблер. Это означает, что функции, не может быть написаны на C или C++, должны быть написаны как подпрограмм или внутренних функций, поддерживаемых компилятором. Некоторые функции являются чувствительны к производительности, а другие — нет. Функции, чувствительные к производительности должны быть реализованы как встроенные функции.  
  
 Компилятор поддерживает встроенные функции описаны в [встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)