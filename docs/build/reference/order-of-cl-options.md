---
title: Порядок параметров CL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 165e20eefecd20ad9dec9e01b38c5eaa7926e4eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372813"
---
# <a name="order-of-cl-options"></a>Порядок параметров CL
Параметры могут находиться в любом в командной строке компилятора CL, за исключением параметра/Link, который должен стоять последним. Компилятор начинается с параметрами, заданными в [переменной среды компилятора CL](../../build/reference/cl-environment-variables.md) и затем читает командную строку слева направо, обрабатывая командные файлы в порядке их обнаружения. Каждый параметр применяется ко всем файлам в командной строке. Если CL встречает несовместимые параметры, используется параметр справа.  
  
## <a name="see-also"></a>См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)