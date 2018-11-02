---
title: Переменные среды инструмента LINK
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
ms.openlocfilehash: 3a398787530794f5a08d6cd122e55c305e265062
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434415"
---
# <a name="link-environment-variables"></a>Переменные среды инструмента LINK

Средство LINK использует следующие переменные среды:

- ССЫЛКИ и \_ССЫЛКУ\_, если определен. Средство LINK добавляет параметры и аргументы, заданные в переменной среды LINK и добавляет параметры и аргументы определены в \_ССЫЛКУ\_ переменную среды, чтобы аргументы командной строки перед обработкой.

- LIB, если определено. Средство LINK использует путь LIB при поиске объекта, библиотеки или другого файла, указанного в командной строке или с помощью [/BASE](../../build/reference/base-base-address.md) параметр. Средство также использует путь LIB для поиска PDB-файла, указанного в объекте. Переменная LIB может содержать один или несколько путей, разделенных точкой с запятой. Один путь должен указывать на подкаталог \lib папки установки Visual C++.

- PATH, если средству необходимо запускать программу CVTRES и не удается найти файл в том же каталоге, где находится LINK. (CVTRES необходима LINK для связи с RES-файлом.) Переменная PATH должна указывать на подкаталог \bin папки установки Visual C++.

- TMP для указания каталога при связывании OMF или RES-файлов.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
[Создание кода C/C++ в командной строке](../../build/building-on-the-command-line.md)<br/>
[Установка переменных пути и среды при построении из командной строки](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
