---
title: Ошибка средств компоновщика LNK1158
ms.date: 11/04/2016
f1_keywords:
- LNK1158
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
ms.openlocfilehash: f2e3e1d9948960beed631861c5981f2d09daf632
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455943"
---
# <a name="linker-tools-error-lnk1158"></a>Ошибка средств компоновщика LNK1158

не удается запустить «имя_файла»

Данного исполняемого файла, вызывается [ССЫЛКУ](../../build/reference/linker-command-line-syntax.md) не в каталог, содержащий ССЫЛКУ, так и в каталоге, указанном в переменной среды PATH.

Например, эта ошибка может возникнуть при попытке использовать параметр PGOPTIMIZE [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) параметр компоновщика на компьютере с 32-разрядной операционной системе.