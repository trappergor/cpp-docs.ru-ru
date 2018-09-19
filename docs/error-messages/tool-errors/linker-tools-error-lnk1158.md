---
title: Ошибка средств компоновщика LNK1158 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1158
dev_langs:
- C++
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce319aa4529c74cad00342b09aa0ed98bb49ce7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094173"
---
# <a name="linker-tools-error-lnk1158"></a>Ошибка средств компоновщика LNK1158

не удается запустить «имя_файла»

Данного исполняемого файла, вызывается [ССЫЛКУ](../../build/reference/linker-command-line-syntax.md) не в каталог, содержащий ССЫЛКУ, так и в каталоге, указанном в переменной среды PATH.

Например, эта ошибка может возникнуть при попытке использовать параметр PGOPTIMIZE [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) параметр компоновщика на компьютере с 32-разрядной операционной системе.