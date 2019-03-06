---
title: Порядок параметров CL
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: d87e3214d4829f81258acd00abebced34d7d969d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423694"
---
# <a name="order-of-cl-options"></a>Порядок параметров CL

Параметры могут находиться в любом в командной строке компилятора CL, за исключением параметра/Link, который должен стоять последним. Компилятор начинается с параметрами, заданными в [переменной среды компилятора CL](../../build/reference/cl-environment-variables.md) и затем считывает командную строку слева направо — обработка командных файлов, в порядке их обнаружения. Каждый параметр применяется ко всем файлам в командной строке. Если CL встречает несовместимые параметры, он использует крайний правый параметр.

## <a name="see-also"></a>См. также

[Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)
