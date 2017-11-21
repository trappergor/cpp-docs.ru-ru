---
title: "Порядок параметров CL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords: cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fdcc4b315f2e223e59e88e2f5876965d106a49c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="order-of-cl-options"></a>Порядок параметров CL
Параметры могут находиться в любом в командной строке компилятора CL, за исключением параметра/Link, который должен стоять последним. Компилятор начинается с параметрами, заданными в [переменной среды компилятора CL](../../build/reference/cl-environment-variables.md) и затем читает командную строку слева направо, обрабатывая командные файлы в порядке их обнаружения. Каждый параметр применяется ко всем файлам в командной строке. Если CL встречает несовместимые параметры, используется параметр справа.  
  
## <a name="see-also"></a>См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)