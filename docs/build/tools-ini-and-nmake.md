---
title: "Tools.ini и NMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "программа NMAKE, чтение файлов"
  - "Tools.ini и NMake"
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Tools.ini и NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE считывает файл Tools.ini перед считыванием файлов makefile, если не используется параметр \/R.  Сначала NMAKE ищет Tools.ini в текущем каталоге, а затем в каталоге, указанном в переменной среды INIT.  Раздел параметров NMAKE в файле настройки начинается с метки `[NMAKE]` и может содержать любые сведения о файле makefile.  Комментарий следует размещать на отдельной строке, в начале разместив знак номера \(\#\).  
  
## См. также  
 [Запуск программы NMAKE](../build/running-nmake.md)