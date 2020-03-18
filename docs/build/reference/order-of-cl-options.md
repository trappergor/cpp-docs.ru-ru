---
title: Порядок параметров CL (C++) — Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 6c57a68dd15d82a9d6a01bfe145374bda6eb1510
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439197"
---
# <a name="order-of-cl-options"></a>Порядок параметров CL

Параметры могут находиться в любом месте командной строки CL, за исключением параметра/link, который должен быть последним. Компилятор начинается с параметров, указанных в [переменной среды CL](cl-environment-variables.md) , а затем считывает командную строку слева направо — обрабатывая командные файлы в том порядке, в котором они встречаются. Каждый параметр применяется ко всем файлам в командной строке. Если CL обнаруживает конфликтующие параметры, используется самый правый параметр.

## <a name="see-also"></a>См. также раздел

[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
