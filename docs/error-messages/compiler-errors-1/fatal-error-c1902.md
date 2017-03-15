---
title: "Неустранимая ошибка C1902 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 79987719614dfa3075f9a9090ca1d97f6546ceb3
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1902"></a>Неустранимая ошибка C1902
несоответствие диспетчера базы данных программы; Проверьте установку  
  
Файл базы данных программы (.pdb) был создан в более поздней версии mspdb*XXX*.dll, чем компилятор обнаружил в системе. Эта ошибка обычно указывает, что mspdbsrv.exe mspdbcore.dll отсутствуют или имеются разные версии, чем mspdb*XXX*DLL-файл. ( *XXX* заполнитель в mspdb*XXX*имя файла .dll изменяется с каждым выпуском продукта. Например, в Visual Studio 2015 файл называется mspdb140.dll.)  
  
Убедитесь, соответствующие версии mspdbsrv.exe mspdbcore.dll и mspdb*XXX*.dll, установленных в системе. Убедитесь, что несовпадение версий не были скопированы в каталог, содержащий инструменты компиляции и компоновки для целевой платформы. Например, вы может скопировать файлы чтобы вызывать компилятор или компоновщик средство из командной строки без настройки **путь** переменной среды соответствующим образом.
