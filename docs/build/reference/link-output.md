---
title: Выходные данные LINK
ms.date: 11/04/2016
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
ms.openlocfilehash: 8323723f2049d3db469e874c91b99f4cfb561c72
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439313"
---
# <a name="link-output"></a>Выходные данные LINK

В выходные данные ссылки входят exe-файлы, библиотеки DLL, сопоставления и сообщения.

##  <a name="_core_output_files"></a>Выходные файлы

Выходным файлом по умолчанию является EXE-файл. Если указан параметр [/DLL](dll-build-a-dll.md) , LINK создает DLL-файл. Имя выходного файла можно контролировать с помощью параметра [имя выходного файла (/out)](out-output-file-name.md) .

В инкрементном режиме LINK создает ILK файл для хранения сведений о состоянии для последующих добавочных сборок программы. Дополнительные сведения о ILK Files см. в разделе [. ILK](dot-ilk-files-as-linker-input.md). Дополнительные сведения о инкрементной компоновке см. в разделе [добавочная ссылка (/incremental)](incremental-link-incrementally.md) .

Когда LINK создает программу, содержащую операции экспорта (обычно это DLL), она также создает LIB-файл, если в сборке не был использован файл EXP. С помощью параметра [/ImpLib](implib-name-import-library.md) можно управлять именем файла библиотеки импорта.

Если указан параметр [Generate сопоставления (/Map)](map-generate-mapfile.md) , LINK создает объект сопоставления.

Если указан параметр [создать отладочную информацию (/Debug)](debug-generate-debug-info.md) , LINK создает PDB-файл, содержащий отладочную информацию для программы.

##  <a name="_core_other_output"></a>Другие выходные данные

При вводе `link` без каких-либо других входных данных из командной строки LINK отображает инструкцию по использованию, которая суммирует параметры.

ССЫЛКА отображает сообщение об авторских правах и версии, а также выводит на экран Ввод командного файла, если не используется параметр [отключить баннер запуска (/NOLOGO)](nologo-suppress-startup-banner-linker.md) .

Для отображения дополнительных сведений о сборке можно использовать параметр [Печать сообщений о ходе выполнения (/verbose)](verbose-print-progress-messages.md) .

LINK выдает сообщения об ошибках и предупреждения в формате LNK*nnnn*. Этот префикс ошибки и диапазон номеров также используются службами LIB, DUMPBIN и EDITBIN.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
