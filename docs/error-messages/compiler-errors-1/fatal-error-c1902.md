---
title: Неустранимая ошибка C1902 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23507b6531f9ee4e5ce5efd5b60a1977206635c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1902"></a>Неустранимая ошибка C1902
несоответствие диспетчера базы данных программы; Проверьте установленную копию  
  
Файл базы данных программы (PDB-файл) был создан с помощью более новой версии mspdb*XXX*.dll от того, компилятор обнаружил в вашей системе. Эта ошибка обычно указывает, что mspdbsrv.exe или mspdbcore.dll отсутствуют или имеются разные версии, чем mspdb*XXX*DLL-файл. ( *XXX* заполнителя в mspdb*XXX*имени файла .dll изменяется с каждым выпуском продукта. Например, в Visual Studio 2015 имя файла — mspdb140.dll.)  
  
Убедитесь, соответствующие версии mspdbsrv.exe mspdbcore.dll и mspdb*XXX*.dll, установленных в системе. Убедитесь, что несовпадение версий не были скопированы в каталог, содержащий инструменты компиляции и компоновки для целевой платформы. Например, вы могли быть скопированы файлы чтобы удалось вызвать компилятор или компоновщик средство из командной строки без параметра **путь** переменной среды соответствующим образом.