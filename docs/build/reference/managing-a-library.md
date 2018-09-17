---
title: Управление библиотекой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
dev_langs:
- C++
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd6fff812d200e16b82994f9f9bbe598aface547
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713158"
---
# <a name="managing-a-library"></a>Управление библиотекой

Режим по умолчанию для LIB — позволяют создавать и изменять библиотеки объектов COFF. LIB запускается в этом режиме, если вы не укажете/extract (для копирования объекта в файл) или/DEF (для построения библиотеки импорта).

Чтобы построить библиотеку из объектов и библиотек, используйте следующий синтаксис:

```
LIB [options...] files...
```

Эта команда создает библиотеку входных данных в один или несколько *файлы*. *Файлы* может быть объект COFF-файлы, объект OMF 32-разрядные файлы или существующих COFF-библиотеками. LIB создает одну библиотеку, которая содержит все объекты в указанных файлах. Если входной файл является файлом объект OMF 32-разрядной, LIB преобразует его в COFF перед построением библиотеки. LIB не может принимать объект OMF 32-разрядной, который находится в библиотеке, созданной с 16-разрядной версии LIB. Сначала необходимо использовать 16-разрядное LIB для извлечения объекта. Затем можно использовать как входные данные для 32-разрядной LIB извлеченного файла.

По умолчанию LIB присваивает выходного файла, используя базовое имя первого файла объекта или библиотеки и расширение. lib. Выходной файл помещается в текущем каталоге. Если файл с таким именем уже существует, выходной файл заменяет существующий файл. Чтобы сохранить существующую библиотеку, используйте параметр/out для указания имени для выходного файла.

Создание и изменение библиотеки применяются следующие параметры.

**/ LIBPATH:** *dir*<br/>
Переопределяет путь к библиотеке среды. Дополнительные сведения см. в описании ссылки [/LIBPATH](../../build/reference/libpath-additional-libpath.md) параметр.

**И ПОЛУЧЕНИЯ СПИСКА**<br/>
Отображает сведения о выходной библиотеке в стандартный вывод. Выходные данные можно перенаправить в файл. / List можно использовать для определения правильного содержания существующей библиотеки без ее изменения.

**/ NAME:** *имя файла*<br/>
При создании библиотеки импорта, указывает имя библиотеки DLL, для которых создается библиотека импорта.

**/ NODEFAULTLIB**<br/>
Удаляет один или несколько стандартных библиотек из списка библиотек, в которой выполняется поиск при разрешении внешних ссылок. См. в разделе [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) Дополнительные сведения.

**/ OUT:** *имя файла*<br/>
Переопределяет имя файла выходных данных по умолчанию. По умолчанию создается выходной библиотеке в текущем каталоге, базовым именем первого файла библиотеки или объекта в командной строке и расширение. lib.

**/ REMOVE:** *объекта*<br/>
Исключает указанный *объект* из выходной библиотеки. LIB создает выходную библиотеку, объединяя все объекты (в объектных файлов или библиотек), а затем удаляет все объекты, указанные с помощью/Remove.

**/ SUBSYSTEM:**{**КОНСОЛИ** &AMP;#124; **EFI_APPLICATION** &AMP;#124; **EFI_BOOT_SERVICE_DRIVER** &AMP;#124; **EFI_ROM** &AMP;#124; **EFI_RUNTIME_DRIVER** &AMP;#124; **СОБСТВЕННОГО** &AMP;#124; **POSIX** &AMP;#124; **WINDOWS** &AMP;#124; **WINDOWSCE**} [, #[. ##]]<br/>
Указывает операционной системе, как запустить программу, созданную путем связывания с выходной библиотеке. Дополнительные сведения см. в описании ссылки [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметр.

LIB-параметры, указанные в командной строке не учитывается регистр.

LIB можно использовать для выполнения следующих задач управления библиотеки:

- Чтобы добавить объекты в библиотеке, укажите имя файла для существующей библиотеки и имена файлов для новых объектов.

- Объединять библиотеки, укажите имя файла библиотеки. Можно добавлять объекты и объединять библиотеки с помощью одной команды LIB.

- Чтобы заменить элемент библиотеки объекта, укажите библиотеку, содержащую объект члена, замены и имя файла для нового объекта (или библиотеку, содержащую его). Если объект с тем же именем существует в более чем один входной файл, LIB помещает последний объект, указанный в команде LIB в выходной библиотеке. Когда вы заменяете члена библиотеки, не забудьте указать нового объекта или библиотеки после библиотеку, содержащую старый объект.

- Чтобы удалить члена из библиотеки, используйте параметр/Remove. LIB обрабатывает все спецификации/Remove после объединения всех входных объектов, независимо от порядка командной строки.

> [!NOTE]
>  Не удается удалить элемент и извлеките его содержимое в файл на том же этапе. Необходимо сначала извлечь объект члена, с помощью/Extract, а затем запустите снова, используя/Remove LIB. Это поведение отличается от 16-разрядное LIB (для OMF-библиотеки), в других продуктов корпорации Майкрософт.

## <a name="see-also"></a>См. также

[Справочник по LIB](../../build/reference/lib-reference.md)