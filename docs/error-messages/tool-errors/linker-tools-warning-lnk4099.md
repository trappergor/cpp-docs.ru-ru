---
title: Предупреждение средств компоновщика LNK4099 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50bdceaba2e72312febec4819b96df334b5398c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026015"
---
# <a name="linker-tools-warning-lnk4099"></a>Предупреждение средств компоновщика LNK4099

Не удалось найти PDB-ФАЙЛ «имя_файла» с «библиотека» или «path»; компоновка объекта выполняется как при отсутствии отладочных данных

Компоновщик не удалось найти PDB-файл. Скопируйте его в каталог, содержащий `object/library`.

Чтобы найти имя PDB-файл, связанный с объектном файле:

1. Извлеките объектный файл из библиотеки с [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.

1. Проверьте путь к PDB-файл с **dumpbin /section:.debug$ T, / RAWDATA** `objectname` **.obj**.

Вы также мог быть скомпилирован с [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), поэтому не нужно использовать, или удалите PDB-файл [/DEBUG](../../build/reference/debug-generate-debug-info.md) параметр компоновщика, если у вас нет PDB-файлы для связываемых объектов.