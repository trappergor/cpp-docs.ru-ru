---
title: Предупреждение средств компоновщика LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: e7139b21f053ea8633356c7194cd719a6a4aef35
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622980"
---
# <a name="linker-tools-warning-lnk4070"></a>Предупреждение средств компоновщика LNK4070

/ Out: имя_файла директивы. EXP отличается от имени выходного файла «имя_файла»; директива игнорируется

`filename` Указано в [имя](../../build/reference/name-c-cpp.md) или [БИБЛИОТЕКИ](../../build/reference/library.md) инструкция, при создании файла .exp отличается от выходных данных `filename` , был либо предполагается, что по умолчанию или определен при помощи [/OUT](../../build/reference/out-output-file-name.md) параметр.

Вы увидите это предупреждение, если изменить имя выходного файла, в среде разработки и где DEF-файл проекта не был обновлен. Вручную обновите DEF-файл, чтобы устранить это предупреждение.

Клиентской программы, которая использует полученный DLL могут возникнуть проблемы.