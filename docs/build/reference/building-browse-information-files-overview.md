---
title: 'Файлов информации обзора построение: Обзор | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2306c69c219320e11259ba6303b76588db8f7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="building-browse-information-files-overview"></a>Информационные файлы просмотра сборки: общие сведения
Чтобы создать сведения о просмотре для просмотра символов, компилятор создает SBR-файл для каждого исходного файла в вашем проекте, затем BSCMAKE. EXE объединяет SBR-файлов в один BSC-файл.  
  
 Создание файлов SBR и BSC занимает некоторое время, поэтому Visual C++ эти функции по умолчанию отключает. Если вы хотите просмотреть текущую информацию, необходимо включить параметры просмотра и повторного построения проекта.  
  
 Используйте [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) или [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) сообщить компилятору о необходимости создания SBR-файлов. Чтобы создать BSC-файлы, можно вызвать [BSCMAKE](../../build/reference/bscmake-command-line.md) из командной строки. Использование BSCMAKE из командной строки позволяет более точно контролировать обработку файлы для просмотра информации. В разделе [Справочник по BSCMAKE](../../build/reference/bscmake-reference.md) для получения дополнительной информации.  
  
> [!TIP]
>  Можно включить создание SBR-файла, но оставить отключить создание BSC-файла. Это предоставляет быстрые построения, а также позволяет быстро создавать свежий BSC-файл, включив Создание BSC-файла и затем построения самого проекта.  
  
 Можно уменьшить время, памяти и дискового пространства, необходимого для построения BSC-файла, уменьшив размер BSC-файл.  
  
 В разделе [свойств «Общие» (проект)](../../ide/general-property-page-project.md) сведения о построении файла просмотра в среде разработки.  
  
### <a name="to-create-a-smaller-bsc-file"></a>Для создания меньшего BSC-файла  
  
1.  Используйте [BSCMAKE параметры командной строки](../../build/reference/bscmake-options.md) для исключения данных из файла для просмотра информации.  
  
2.  Не включайте локальные символы в один или несколько SBR-файлов при компиляции или сборке.  
  
3.  Если объектный файл не содержит информацию, необходимую для данной стадии отладки, не указывайте его SBR-файл из команды BSCMAKE при повторном построении файла для просмотра информации.  
  
### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Чтобы объединить сведения о просмотре из нескольких проектов в одном файле просмотра (.bsc)  
  
1.  Не построения BSC-файл на уровне проекта либо используйте параметр/n, чтобы предотвратить усечение SBR-файлов.  
  
2.  После построения всех проектов, запустите BSCMAKE со всеми SBR-файлы в качестве входного. Допускаются подстановочные знаки. Для экземпляра, если у вас есть проект каталоги C:\X, C:\Y и C:\Z с SBR-файлы в их и требуется объединить все в одной BSC-файл, используйте BSCMAKE C:\X\\*.sbr C:\Y\\\*.sbr C:\Z\\\*. c:\whatever_directory\combined.bsc/o SBR для построения объединенного BSC-файл.  
  
## <a name="see-also"></a>См. также  
 [Средства построения C/C++](../../build/reference/c-cpp-build-tools.md)   
 [Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)