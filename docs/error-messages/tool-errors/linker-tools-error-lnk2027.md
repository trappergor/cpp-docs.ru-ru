---
title: Ошибка средств компоновщика LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: 0c531f70f98a017e8b75cceddc684f99d33bc554
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194604"
---
# <a name="linker-tools-error-lnk2027"></a>Ошибка средств компоновщика LNK2027

неразрешенная ссылка на модуль "Module"

Файл, переданный компоновщику, зависит от модуля, который не был указан с помощью **/ASSEMBLYMODULE** , и не передается непосредственно компоновщику.

Чтобы разрешить LNK2027, выполните одно из следующих действий.

- Не передавайте компоновщику файл, имеющий зависимость модуля.

- Укажите модуль с **/ASSEMBLYMODULE**.

- Если модуль является типобезопасным. netmodule, передайте модуль непосредственно в компоновщик.

Дополнительные сведения см. в разделе [/ASSEMBLYMODULE (Добавление модуля MSIL в сборку)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) и [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).
