---
title: "-BIND | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50f2f1856b4718af8e87728a79511d9b18654efb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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