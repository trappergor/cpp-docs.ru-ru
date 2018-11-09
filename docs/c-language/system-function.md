---
title: Функция system
ms.date: 11/04/2016
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
ms.openlocfilehash: db38a9407aa75988779b8a930ac2ccd99c98d1b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520189"
---
# <a name="system-function"></a>Функция system

**ANSI 4.10.4.5** Содержимое и режим выполнения строки функцией **system**

Функция **system** выполняет внутреннюю команду операционной системы или файл .EXE, .COM (.CMD в Windows NT) или .BAT прямо из программы на языке C, а не в режиме командной строки.

Функция system находит интерпретатор команд (обычно это CMD.EXE в Windows NT или COMMAND.COM в Windows). Затем функция system передает строку аргумента в интерпретатору команд.

Дополнительные сведения см. в описании [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)