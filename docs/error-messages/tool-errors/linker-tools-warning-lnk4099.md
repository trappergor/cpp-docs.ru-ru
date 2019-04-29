---
title: Предупреждение средств компоновщика LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: dcf4d44c3a0b5b10035af763040c2912afc8c6f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310894"
---
# <a name="linker-tools-warning-lnk4099"></a>Предупреждение средств компоновщика LNK4099

Не удалось найти PDB-ФАЙЛ «имя_файла» с «библиотека» или «path»; компоновка объекта выполняется как при отсутствии отладочных данных

Компоновщик не удалось найти PDB-файл. Скопируйте его в каталог, содержащий `object/library`.

Чтобы найти имя PDB-файл, связанный с объектном файле:

1. Извлеките объектный файл из библиотеки с [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.

1. Проверьте путь к PDB-файл с **dumpbin /section:.debug$ T, / RAWDATA** `objectname` **.obj**.

Вы также мог быть скомпилирован с [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), поэтому не нужно использовать, или удалите PDB-файл [/DEBUG](../../build/reference/debug-generate-debug-info.md) параметр компоновщика, если у вас нет PDB-файлы для связываемых объектов.