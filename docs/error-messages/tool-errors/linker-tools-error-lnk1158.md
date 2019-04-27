---
title: Ошибка средств компоновщика LNK1158
ms.date: 11/04/2016
f1_keywords:
- LNK1158
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
ms.openlocfilehash: 0dbb40fb1fe0405f3685a5e7246ecba2b53ec526
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254977"
---
# <a name="linker-tools-error-lnk1158"></a>Ошибка средств компоновщика LNK1158

не удается запустить «имя_файла»

Данного исполняемого файла, вызывается [ССЫЛКУ](../../build/reference/linking.md) не в каталог, содержащий ССЫЛКУ, так и в каталоге, указанном в переменной среды PATH.

Например, эта ошибка может возникнуть при попытке использовать параметр PGOPTIMIZE [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) параметр компоновщика на компьютере с 32-разрядной операционной системе.