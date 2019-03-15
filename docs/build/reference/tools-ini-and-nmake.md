---
title: Tools.ini и NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
ms.openlocfilehash: 38eebb3aaf07438da85b0cfe6bd3f26fb5d6db29
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826863"
---
# <a name="toolsini-and-nmake"></a>Tools.ini и NMAKE

NMAKE считывает Tools.ini, прежде чем он считывает файлы makefile, если не используется /R. Он ищет Tools.ini сначала в текущем каталоге, а затем в каталоге, указанном в переменной среды INIT. Раздел параметров NMAKE в файле настройки начинается с `[NMAKE]` и может содержать любые сведения о файле makefile. Укажите комментарий на отдельные строки, которая начинается со знака номера (#).

## <a name="see-also"></a>См. также

[Запуск программы NMAKE](running-nmake.md)
