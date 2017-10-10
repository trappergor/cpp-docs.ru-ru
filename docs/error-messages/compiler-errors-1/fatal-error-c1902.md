---
title: "Неустранимая ошибка C1902 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 89354565f67c8704eee8c8b5f9dcb94523800c63
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1902"></a>Неустранимая ошибка C1902
несоответствие диспетчера базы данных программы; Проверьте установленную копию  
  
Файл базы данных программы (PDB-файл) был создан с помощью более новой версии mspdb*XXX*.dll от того, компилятор обнаружил в вашей системе. Эта ошибка обычно указывает, что mspdbsrv.exe или mspdbcore.dll отсутствуют или имеются разные версии, чем mspdb*XXX*DLL-файл. ( *XXX* заполнителя в mspdb*XXX*имени файла .dll изменяется с каждым выпуском продукта. Например, в Visual Studio 2015 имя файла — mspdb140.dll.)  
  
Убедитесь, соответствующие версии mspdbsrv.exe mspdbcore.dll и mspdb*XXX*.dll, установленных в системе. Убедитесь, что несовпадение версий не были скопированы в каталог, содержащий инструменты компиляции и компоновки для целевой платформы. Например, вы могли быть скопированы файлы чтобы удалось вызвать компилятор или компоновщик средство из командной строки без параметра **путь** переменной среды соответствующим образом.
