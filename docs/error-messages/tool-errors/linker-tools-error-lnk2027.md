---
title: Ошибка средств компоновщика LNK2027 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 022e363af575e29e3085dcaec21257fa7e4ab5f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116852"
---
# <a name="linker-tools-error-lnk2027"></a>Ошибка средств компоновщика LNK2027

ссылка на неразрешенный модуля «модуль»

Файл, переданный в компоновщик имеет зависимость от модуля, который не был задан с помощью **добавившей** ни напрямую передать в компоновщик.

Чтобы устранить LNK2027, выполните одно из следующих действий.

- Не передавайте компоновщику файл, который зависит от модуля.

- Укажите модуль с помощью **добавившей**.

- При безопасном .netmodule, модуль передайте модуль непосредственно в компоновщик.

Дополнительные сведения см. в разделе [/ASSEMBLYMODULE (Добавление модуля MSIL в сборку)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) и [.netmodule качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).