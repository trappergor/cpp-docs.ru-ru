---
title: Неустранимая ошибка C1902 | Документация Майкрософт
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
ms.openlocfilehash: e5a443b5f80eabe9691cf8ff5220bb9b66da51e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052573"
---
# <a name="fatal-error-c1902"></a>Неустранимая ошибка C1902

несоответствие диспетчера базы данных программы; Проверьте правильность установки

Файл базы данных программы (PDB-файл) был создан с помощью более новой версии mspdb*XXX*.dll, отличного от того, компилятор обнаружил в вашей системе. Эта ошибка обычно указывает, что mspdbsrv.exe или mspdbcore.dll могут отсутствовать или не иметь различные версии, чем mspdb*XXX*DLL-файл. ( *XXX* местозаполнителя в mspdb*XXX*имени файла .dll изменяется с каждым выпуском продукта. Например, в Visual Studio 2015 имя файла — mspdb140.dll.)

Убедитесь, соответствующий версии mspdbsrv.exe mspdbcore.dll и mspdb*XXX*.dll установлены в системе. Убедитесь, что несовпадение версий не были скопированы в каталог, содержащий инструменты компиляции и компоновки для целевой платформы. Например, вы могли быть скопированы файлы чтобы удалось вызвать компилятор или компоновщик средство из командной строки без параметра **путь** переменной среды соответствующим образом.