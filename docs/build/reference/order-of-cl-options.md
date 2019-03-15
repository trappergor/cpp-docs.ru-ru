---
title: Порядок параметров CL (C++) — Visual Studio
ms.date: 12/14/2018
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 93907265bed8141b5c63edd5e75d632e060351fe
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811645"
---
# <a name="order-of-cl-options"></a>Порядок параметров CL

Параметры могут находиться в любом в командной строке компилятора CL, за исключением параметра/Link, который должен стоять последним. Компилятор начинается с параметрами, заданными в [переменной среды компилятора CL](cl-environment-variables.md) и затем считывает командную строку слева направо — обработка командных файлов, в порядке их обнаружения. Каждый параметр применяется ко всем файлам в командной строке. Если CL встречает несовместимые параметры, он использует крайний правый параметр.

## <a name="see-also"></a>См. также

[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
