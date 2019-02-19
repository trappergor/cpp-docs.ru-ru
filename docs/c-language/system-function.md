---
title: Функция system
ms.date: 11/04/2016
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
ms.openlocfilehash: e37de4e084de6727cf2858117945fd162f6b0d63
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151227"
---
# <a name="system-function"></a>Функция system

**ANSI 4.10.4.5** Содержимое и режим выполнения строки функцией **system**

Функция **system** выполняет внутреннюю команду операционной системы или файл .EXE, .COM (.CMD в Windows NT) или .BAT прямо из программы на языке C, а не в режиме командной строки.

Функция system находит интерпретатор команд (обычно это CMD.EXE в Windows NT или COMMAND.COM в Windows). Затем функция system передает строку аргумента в интерпретатору команд.

Дополнительные сведения см. в описании [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
