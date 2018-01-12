---
title: "Управление библиотекой | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05ced49a960aea0b32365b80fe76095893f63d5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="managing-a-library"></a>Управление библиотекой
Режим по умолчанию для LIB — позволяют создавать и изменять библиотеки объектов COFF. LIB запускается в этом режиме, если не указать/extract (для копирования объекта в файл) или/DEF (для построения библиотеки импорта).  
  
 Чтобы построить библиотеку из объектов и библиотек, используйте следующий синтаксис:  
  
```  
LIB [options...] files...  
```  
  
 Эта команда создает библиотеку из одного или нескольких входных данных *файлы*. *Файлы* может быть объект COFF-файлы, файлы объект OMF 32-разрядной или существующие библиотеки COFF. LIB создает одну библиотеку, которая содержит все объекты в указанных файлах. Если входной файл является файлом объект OMF 32 бита, LIB преобразует его в формат COFF перед построением библиотеки. LIB не может принять объект OMF 32-разрядной, который находится в библиотеке, созданной с 16-разрядной версии LIB. 16-разрядное LIB сначала необходимо использовать для извлечения объекта; Затем можно использовать как входные данные для 32-разрядной LIB извлеченного файла.  
  
 По умолчанию LIB присваивает с помощью базового имени первого файла объекта или библиотеки и расширение выходного файла. lib. Выходной файл помещается в текущий каталог. Если файл с таким именем уже существует, выходной файл заменяет существующий файл. Чтобы сохранить существующую библиотеку, необходимо используйте параметр/out для указания имени выходного файла.  
  
 Создание и изменение библиотеки применяются следующие параметры.  
  
 / LIBPATH:`dir`  
 Переопределяет путь к библиотеке среды. Дополнительные сведения см. в описании по ССЫЛКЕ [/LIBPATH](../../build/reference/libpath-additional-libpath.md) параметр.  
  
 / LIST  
 Отображает сведения о выходной библиотеке в стандартный вывод. Результат может быть перенаправлен в файл. / List можно использовать для определения содержания существующей библиотеки, не изменяя его.  
  
 / NAME: *имя файла*  
 При сборке библиотеки импорта задает имя библиотеки DLL, для которых создается библиотека импорта.  
  
 /NODEFAULTLIB  
 Удаляет один или несколько стандартных библиотек из списка библиотек, в которых осуществляется поиск при разрешении внешних ссылок. В разделе [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) для получения дополнительной информации.  
  
 / OUT: *имя файла*  
 Переопределяет имя выходного файла по умолчанию. По умолчанию создается выходной библиотеке в текущем каталоге с базовым именем первого файла библиотеки или объекта в командной строке и расширение. lib.  
  
 / REMOVE: *объект*  
 Исключает указанный *объекта* из выходной библиотеки. LIB создает выходную библиотеку, объединяя все объекты (в объектных файлов или библиотек), а затем удаляет все объекты, указанные в параметре/Remove.  
  
 / SUBSYSTEM: {КОНСОЛИ &#124; EFI_APPLICATION &#124; EFI_BOOT_SERVICE_DRIVER &#124; EFI_ROM &#124; EFI_RUNTIME_DRIVER &#124; МАШИННЫЙ КОД &#124; POSIX &#124; WINDOWS &#124; WINDOWSCE} [, #[. ##]]  
 Указывает операционной системе, как запустить программу, созданную путем связывания с выходной библиотеки. Дополнительные сведения см. в описании по ССЫЛКЕ [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметр.  
  
 LIB-параметры, указанные в командной строке не учитывается регистр.  
  
 LIB можно использовать для выполнения следующих задач управления библиотеки:  
  
-   Чтобы добавить объекты в библиотеке, укажите имя файла для существующей библиотеки и имена файлов для новых объектов.  
  
-   Объединять библиотеки, укажите имя файла библиотеки. Можно добавлять объекты и объединять библиотеки с помощью одной команды LIB.  
  
-   Чтобы заменить элемент библиотеки объекта, укажите библиотеку, содержащую заменяемый объект члена и имя файла для нового объекта (или библиотеки, содержащей его). Если объект с тем же именем существует в более чем один входной файл, LIB помещает последний объект, указанный в команде LIB в выходную библиотеку. При замене члена библиотеки не забудьте указать после библиотеку, содержащую старый объект нового объекта или библиотеки.  
  
-   Чтобы удалить элемент из библиотеки, используйте параметр/Remove. LIB обрабатывает все спецификации параметра/Remove после объединения всех входных объектов независимо от порядка командной строки.  
  
> [!NOTE]
>  Не удается удалить элемент и извлеките его в файл на том же этапе. Необходимо сначала извлечь объект члена с помощью/Extract, а затем запустить LIB снова, используя/Remove. Это поведение отличается от 16-разрядное LIB (для библиотек OMF), предоставляемых в других продуктах Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Справочник по LIB](../../build/reference/lib-reference.md)