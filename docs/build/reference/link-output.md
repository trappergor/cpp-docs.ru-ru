---
title: Выходные данные LINK
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 183f83501d930188032ec4209623ef7cf1a30efa
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807628"
---
# <a name="link-output"></a>Выходные данные LINK

Выходные данные Link включает файлы .exe, библиотеки DLL, файлы сопоставления и сообщения.

##  <a name="_core_output_files"></a> Выходные файлы

Выходной файл по умолчанию, перейдя по ССЫЛКЕ — это файл .exe. Если [/DLL](dll-build-a-dll.md) параметр указан, программа LINK создает DLL-файл. Можно задать имя выходного файла с [имя выходного файла (/ OUT)](out-output-file-name.md) параметр.

В инкрементном режиме LINK создает ILK-файл, сведения о состоянии для более поздней версии инкрементные сборки программы. Дополнительные сведения о ILK-файлы, см. в разделе [ILK-файлы](dot-ilk-files-as-linker-input.md). Дополнительные сведения о инкрементную компоновку, см. в разделе [инкрементная компоновка (/ INCREMENTAL)](incremental-link-incrementally.md) параметр.

При LINK создает программу, содержащую экспортирует (обычно DLL), но и LIB-файл, если EXP-файл был использован в сборке. Можно задать имя файла библиотеки импорта с [/IMPLIB](implib-name-import-library.md) параметр.

Если [Создание файла сопоставления (/ MAP)](map-generate-mapfile.md) параметр указан, LINK создает файл сопоставления.

Если [создать отладочную информацию (/ DEBUG)](debug-generate-debug-info.md) параметр указан, LINK создает PDB-ФАЙЛ содержит отладочную информацию для программы.

##  <a name="_core_other_output"></a> Прочие выходные данные

При вводе `link` без других командной строки ввода, ссылка отображает инструкцию использования параметров.

ССЫЛКА отображает сообщение об авторских правах и версии и выводит командного файла ввода, если не [отключить загрузочное объявление (/ NOLOGO)](nologo-suppress-startup-banner-linker.md) используется параметр.

Можно использовать [печать сообщений о ходе выполнения (/ VERBOSE)](verbose-print-progress-messages.md) параметр для отображения дополнительных сведений о сборке.

ССЫЛКА выдает сообщения об ошибках и предупреждения в виде LNK*nnnn*. Этот префикс ошибки и диапазон номеров, также используются, LIB, DUMPBIN и EDITBIN.

## <a name="see-also"></a>См. также

[Справочник по MSVC компоновщика](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
