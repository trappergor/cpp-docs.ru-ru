---
title: Запуск программы NMAKE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6c39612cf4df47665f7ea3d529b77ee4e70ce8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="running-nmake"></a>Запуск программы NMAKE
## <a name="syntax"></a>Синтаксис  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## <a name="remarks"></a>Примечания  
 Только указанные сборки NMAKE *цели* или, если он не задан, первый для целевых платформ в файле makefile. Первый целевой объект файла makefile может быть [псевдоцелью](../build/pseudotargets.md) , создающим другие целевые объекты. Программа NMAKE использует сборочных файлов проекта, указанный в параметре /F; Если /F не указан, используется файл Makefile в текущем каталоге. Если файл makefile не указан, он использует правила вывода для построения командной строки *цели*.  
  
 `commandfile` Текстовый файл (или файл ответов) содержит данные в командной строке. Другие входные данные могут указываться перед или после`commandfile`. Допускается указание пути. В `commandfile`, разрывы строк обрабатываются как пробелы. Макроопределения следует заключайте в кавычки, если они содержат пробелы.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Параметры NMAKE](../build/nmake-options.md)  
  
 [Tools.ini и NMAKE](../build/tools-ini-and-nmake.md)  
  
 [Коды выхода из NMAKE](../build/exit-codes-from-nmake.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по программе NMAKE](../build/nmake-reference.md)