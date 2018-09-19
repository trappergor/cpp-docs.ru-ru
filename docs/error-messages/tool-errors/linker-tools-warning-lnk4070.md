---
title: Предупреждение средств компоновщика LNK4070 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4070
dev_langs:
- C++
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cfb4ae1c5440742c491d9615a2b4929a9b04f66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106964"
---
# <a name="linker-tools-warning-lnk4070"></a>Предупреждение средств компоновщика LNK4070

/ Out: имя_файла директивы. EXP отличается от имени выходного файла «имя_файла»; директива игнорируется

`filename` Указано в [имя](../../build/reference/name-c-cpp.md) или [БИБЛИОТЕКИ](../../build/reference/library.md) инструкция, при создании файла .exp отличается от выходных данных `filename` , был либо предполагается, что по умолчанию или определен при помощи [/OUT](../../build/reference/out-output-file-name.md) параметр.

Вы увидите это предупреждение, если изменить имя выходного файла, в среде разработки и где DEF-файл проекта не был обновлен. Вручную обновите DEF-файл, чтобы устранить это предупреждение.

Клиентской программы, которая использует полученный DLL могут возникнуть проблемы.