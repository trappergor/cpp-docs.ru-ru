---
title: Переменные среды инструмента LINK | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 076e427e50520651f30cde20c764ff1124a6f953
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372702"
---
# <a name="link-environment-variables"></a>Переменные среды инструмента LINK

Средство LINK использует следующие переменные среды:  
  
-   ССЫЛКИ и \_ССЫЛКУ\_, если определен. LINK добавляет параметры и аргументы, заданные в переменной среды LINK и добавляет параметры и аргументы, определенные в \_ССЫЛКУ\_ переменной среды аргументов командной строки перед обработкой.  
  
-   LIB, если определено. Средство LINK использует путь LIB при поиске объекта, библиотеки или другого файла, указанного в командной строке, или [/BASE](../../build/reference/base-base-address.md) параметр. Средство также использует путь LIB для поиска PDB-файла, указанного в объекте. Переменная LIB может содержать один или несколько путей, разделенных точкой с запятой. Один путь должен указывать на подкаталог \lib папки установки Visual C++.  
  
-   PATH, если средству необходимо запускать программу CVTRES и не удается найти файл в том же каталоге, где находится LINK. (CVTRES необходима LINK для связи с RES-файлом.) Переменная PATH должна указывать на подкаталог \bin папки установки Visual C++.  
  
-   TMP для указания каталога при связывании OMF или RES-файлов.  
  
## <a name="see-also"></a>См. также  

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
[Параметры компоновщика](../../build/reference/linker-options.md)   
[Создание кода C/C++ в командной строке](../../build/building-on-the-command-line.md)  
[Установка переменных пути и среды при построении из командной строки](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
