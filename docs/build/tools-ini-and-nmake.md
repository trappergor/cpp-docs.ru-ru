---
title: "Tools.ini и NMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 638132f640fd342a752ec45541275178f6f26692
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini и NMAKE
NMAKE считывает Tools.ini прежде чем он считывает makefile-файлы, если только не используется /R. Ищет Tools.ini сначала в текущем каталоге, а затем в каталоге, указанном в переменной среды INIT. Раздел параметров NMAKE в файле настройки начинается с `[NMAKE]` и может содержать любые сведения о файле makefile. Укажите комментарий на отдельные строки, начинающиеся со знака номера (#).  
  
## <a name="see-also"></a>См. также  
 [Запуск программы NMAKE](../build/running-nmake.md)