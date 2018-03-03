---
title: "Tools.ini и NMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4516c3206a08c2b9ee32aea4bbb669ce4cdf0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini и NMAKE
NMAKE считывает Tools.ini прежде чем он считывает makefile-файлы, если только не используется /R. Ищет Tools.ini сначала в текущем каталоге, а затем в каталоге, указанном в переменной среды INIT. Раздел параметров NMAKE в файле настройки начинается с `[NMAKE]` и может содержать любые сведения о файле makefile. Укажите комментарий на отдельные строки, начинающиеся со знака номера (#).  
  
## <a name="see-also"></a>См. также  
 [Запуск программы NMAKE](../build/running-nmake.md)