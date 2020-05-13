---
title: Управление библиотекой
ms.date: 11/04/2016
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
ms.openlocfilehash: de55059834a0887d487b7be38377af9984512b75
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336409"
---
# <a name="managing-a-library"></a>Управление библиотекой

Режим по умолчанию для LIB заключается в создании или изменении библиотеки объектов COFF. LIB работает в этом режиме, если вы не указываете /EXTRACT (для копирования объекта в файл) или /DEF (для создания библиотеки импорта).

Для создания библиотеки из объектов и/или библиотек используйте следующий синтаксис:

```
LIB [options...] files...
```

Эта команда создает библиотеку из одного или нескольких *входных файлов.* *Файлы* могут быть файлами объектов COFF, 32-битными файлами объектов OMF или существующими библиотеками COFF. LIB создает одну библиотеку, которая содержит все объекты в указанных файлах. Если вхотворный файл представляет собой 32-разрядный файл объектов OMF, LIB преобразует его в COFF перед созданием библиотеки. LIB не может принять 32-битный объект OMF, наемный в библиотеке, созданной 16-битной версией LIB. Вы должны сначала использовать 16-битный LIB для извлечения объекта; затем вы можете использовать извлеченный файл объекта в качестве ввода в 32-битный LIB.

По умолчанию LIB называет выходный файл, используя базовое имя первого файла объекта или библиотеки и расширение .lib. Файл вывода помещается в текущий каталог. Если файл уже существует с тем же именем, выводной файл заменяет существующий файл. Чтобы сохранить существующую библиотеку, используйте опцию /OUT, чтобы указать имя для выходного файла.

Следующие варианты применяются к созданию и изменению библиотеки:

**/LIBPATH:** *реж.*<br/>
Переопределяет путь к библиотеке среды. Для получения подробной информации смотрите описание опции LINK [/LIBPATH.](libpath-additional-libpath.md)

**/СПИСОК**<br/>
Отображает информацию о библиотеке вывода в стандартный вывод. Выход может быть перенаправлен в файл. Вы можете использовать /LIST для определения содержимого существующей библиотеки без ее изменения.

**/NAME:** *имя файла*<br/>
При создании библиотеки импорта указывается название DLL, для которого строится импортная библиотека.

**/NODEFAULTLIB**<br/>
Удаляет одну или несколько библиотек по умолчанию из списка библиотек, которые он ищет при решении внешних ссылок. Дополнительную информацию можно узнать [по смотреть в /NODEFAULTLIB.](nodefaultlib-ignore-libraries.md)

**/OUT:** *имя файла*<br/>
Переопределяет имя вывода по умолчанию. По умолчанию библиотека вывода создается в текущем каталоге с базовым именем первого файла библиотеки или файла объекта в командной строке и расширением .lib.

**/REMOVE:** *объект*<br/>
Опускает указанный *объект* из библиотеки вывода. LIB создает библиотеку вывода, комбинируя все объекты (будь то в файлах объектов или библиотеках), а затем удаляя любые объекты, указанные с /REMOVE.

**/SUBSYSTEM:**-**КОНСОЛя** &#124; EFI_APPLICATION &#124; **EFI_BOOT_SERVICE_DRIVER** **EFI_BOOT_SERVICE_DRIVER** &#124; EFI_ROM **EFI_RUNTIME_DRIVER** &#124; **EFI_ROM** &#124; &#124; **&#124;** **СУТОв** &#124;с &#124; **WindowsCE.** **WINDOWS**<br/>
Сообщает операционной системе, как запустить программу, созданную путем ссылки на библиотеку вывода. Для получения дополнительной информации смотрите описание опции LINK [/SUBSYSTEM.](subsystem-specify-subsystem.md)

Параметры LIB, указанные в командной строке, не являются чувствительными к случаю.

Вы можете использовать LIB для выполнения следующих задач по управлению библиотекой:

- Чтобы добавить объекты в библиотеку, укажите имя файла для существующей библиотеки и имена файлов для новых объектов.

- Чтобы объединить библиотеки, укажите имена файлов библиотеки. Можно добавлять объекты и объединять библиотеки с одной командой LIB.

- Чтобы заменить участника библиотеки новым объектом, укажите библиотеку, содержащую объект-член, который должен быть заменен, и имя файла для нового объекта (или библиотеки, которая его содержит). Когда объект с одинаковым именем существует в более чем одном файле ввода, LIB помещает последний объект, указанный в команде LIB, в библиотеку вывода. При замене члена библиотеки обязательно укажите новый объект или библиотеку после библиотеки, содержащей старый объект.

- Чтобы удалить участника из библиотеки, используйте опцию /REMOVE. LIB обрабатывает любые спецификации /REMOVE после объединения всех входных объектов, независимо от заказа командной строки.

> [!NOTE]
> Вы не можете удалить участника и извлечь его в файл в том же шаге. Сначала необходимо извлечь объект-член с помощью /EXTRACT, а затем снова запустить LIB с помощью /REMOVE. Такое поведение отличается от 16-битной LIB (для библиотек OMF), предоставляемой в других продуктах Майкрософт.

## <a name="see-also"></a>См. также раздел

[Справочник по LIB](lib-reference.md)
