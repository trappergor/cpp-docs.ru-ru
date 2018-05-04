---
title: -BIND | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bind
dev_langs:
- C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b77c778017dc78235948e8d23db136c1f63ab12d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="bind"></a>/BIND
```  
/BIND[:PATH=path]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр задает адреса точек входа в таблице адресов импорта исполняемого файла или библиотеки DLL. Используйте этот параметр, чтобы уменьшить время загрузки программы.  
  
 Укажите исполняемый файл и DLL-библиотеки в программе *файлы* аргумент в командной строке EDITBIN. Необязательный *путь* аргумент/BIND задает расположение библиотек DLL, используемых в указанных файлах. Несколько каталогов отделяются точкой с запятой (**;**). Если *путь* не указан, программа EDITBIN ВЕДЕТ поиск в каталогах, указанных в переменной среды PATH. Если *путь* указан, программа EDITBIN игнорирует переменной PATH.  
  
 По умолчанию загрузчик программ задает адреса точек входа при загрузке программы. Количество времени, этот процесс занимает зависит от числа библиотек DLL и число точек входа, используемых в программе. Если программа была изменена с/BIND и базовые адреса исполняемого файла и ее DLL не конфликтуют с библиотеками DLL, которые уже загружены, операционная система не нужно задавать эти адреса. В ситуации, где неправильно основаны файлы операционная система перемещает библиотек DLL программы и повторно вычисляет адреса точек входа, что увеличивает время загрузки программы.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)