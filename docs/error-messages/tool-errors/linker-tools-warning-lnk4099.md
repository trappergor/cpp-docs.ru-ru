---
title: Предупреждение средств компоновщика LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: b1f330924b8e47e0649268142106a050c83cb20a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183323"
---
# <a name="linker-tools-warning-lnk4099"></a>Предупреждение средств компоновщика LNK4099

PDB-файл "имяфайла" не найден с "объект/библиотека" или "путь"; Компоновка объекта как при отсутствии отладочной информации

Компоновщику не удалось найти PDB-файл. Скопируйте его в каталог, содержащий `object/library`.

Чтобы найти имя PDB-файла, связанного с объектом Object File, выполните следующие действия.

1. Извлеките объектный файл из библиотеки с помощью программы [lib](../../build/reference/lib-reference.md) **/Extract:** `objectname` **. obj** `xyz` **. lib**.

1. Проверьте путь к PDB-файлу с помощью **dumpbin/Section:. debug $ T/равдата** `objectname` **. obj**.

Можно также выполнить компиляцию с помощью [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), чтобы не нужно было использовать PDB, или удалите параметр компоновщика [/Debug](../../build/reference/debug-generate-debug-info.md) , если у вас нет PDB-файлов для связываемых объектов.
