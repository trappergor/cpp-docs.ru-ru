---
title: Ошибка средств компоновщика LNK1332 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1332
dev_langs:
- C++
helpviewer_keywords:
- LNK1332
ms.assetid: b31d5ca0-c27f-4177-896b-2637dccbde24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b256c61b9e9de6bf19e754054de1f55fcdec5f0b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094524"
---
# <a name="linker-tools-error-lnk1332"></a>Ошибка средств компоновщика LNK1332

обнаружено\<count > типы среды выполнения Windows, импортированных в один модуль и определен в другом модуле

Когда он преобразовывался в текущий целевой объект, Компоновщик обнаружил <`count`> типы среды выполнения Windows, каждый из которых импортируется в одном модуле и в другом модуле также определен.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Исправьте все ошибки LNK2039 в сборке, в соответствии с рекомендация в сообщении об ошибке.

## <a name="see-also"></a>См. также

[Ошибка средств компоновщика LNK2039](../../error-messages/tool-errors/linker-tools-error-lnk2039.md)<br/>
[Ошибки и предупреждения средств компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)