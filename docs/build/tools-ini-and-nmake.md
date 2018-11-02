---
title: Tools.ini и NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
ms.openlocfilehash: 1a8673741cb49c504855fb1af00dbdc06379210d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654419"
---
# <a name="toolsini-and-nmake"></a>Tools.ini и NMAKE

NMAKE считывает Tools.ini, прежде чем он считывает файлы makefile, если не используется /R. Он ищет Tools.ini сначала в текущем каталоге, а затем в каталоге, указанном в переменной среды INIT. Раздел параметров NMAKE в файле настройки начинается с `[NMAKE]` и может содержать любые сведения о файле makefile. Укажите комментарий на отдельные строки, которая начинается со знака номера (#).

## <a name="see-also"></a>См. также

[Запуск программы NMAKE](../build/running-nmake.md)