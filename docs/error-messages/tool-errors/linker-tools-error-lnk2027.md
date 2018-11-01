---
title: Ошибка средств компоновщика LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: e74912780bab3056ead36ae3705f0910805228e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545903"
---
# <a name="linker-tools-error-lnk2027"></a>Ошибка средств компоновщика LNK2027

ссылка на неразрешенный модуля «модуль»

Файл, переданный в компоновщик имеет зависимость от модуля, который не был задан с помощью **добавившей** ни напрямую передать в компоновщик.

Чтобы устранить LNK2027, выполните одно из следующих действий.

- Не передавайте компоновщику файл, который зависит от модуля.

- Укажите модуль с помощью **добавившей**.

- При безопасном .netmodule, модуль передайте модуль непосредственно в компоновщик.

Дополнительные сведения см. в разделе [/ASSEMBLYMODULE (Добавление модуля MSIL в сборку)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) и [.netmodule качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).