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
ms.openlocfilehash: 253f88ed50b9f064edf976277a4618e4f101ec7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331792"
---
# <a name="link-output"></a>Выходные данные LINK

Выход ссылки включает файлы .exe, DLL, mapfiles и сообщения.

## <a name="output-files"></a><a name="_core_output_files"></a>Файлы вывода

Выводной файл по умолчанию из LINK — это файл .exe. Если опция [/DLL](dll-build-a-dll.md) указана, LINK создает файл .dll. Вы можете управлять именем файла вывода с помощью опции [«Имя файла вывода» (/OUT).](out-output-file-name.md)

В инкрементном режиме LINK создает файл .ilk для хранения информации о состоянии для последующих дополнительных сборок программы. Для получения подробной информации [.ilk Files](dot-ilk-files-as-linker-input.md)о файлах .ilk см. Для получения дополнительной информации о [Link Incrementally (/INCREMENTAL)](incremental-link-incrementally.md) дополнительной увязке см.

Когда LINK создает программу, содержащую экспорт (обычно DLL), он также создает файл .lib, если в сборке не был использован файл .exp. Вы можете управлять именем файла библиотеки импорта с опцией [/IMPLIB.](implib-name-import-library.md)

Если указан [параметр Generate Mapfile (/MAP),](map-generate-mapfile.md) LINK создает картографический файл.

Если указана опция [Generate Debug Info (/DEBUG),](debug-generate-debug-info.md) LINK создает PDB, чтобы содержать информацию об отладке для программы.

## <a name="other-output"></a><a name="_core_other_output"></a>Прочие выходные

При вводе `link` без каких-либо других входных данных командной строки LINK отображает заявление об использовании, которое обобщает его параметры.

LINK отображает сообщение об авторском праве и версии и отголоски ввода командного файла, если только не используется опция [«Баннер запуска» (/NOLOGO).](nologo-suppress-startup-banner-linker.md)

Для отображения дополнительных сведений о сборке можно использовать опцию [Print Progress Messages (/VERBOSE).](verbose-print-progress-messages.md)

LINK выдает сообщения об ошибках и предупреждениях в виде LNK*nnnn*. Эта приставка ошибки и диапазон чисел также используются LIB, DUMPBIN и EDITBIN.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Варианты MSVC Linker](linker-options.md)
