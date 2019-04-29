---
title: Предупреждение средств компоновщика LNK4022
ms.date: 11/04/2016
f1_keywords:
- LNK4022
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
ms.openlocfilehash: 1c9ccfe6ca201ae4deed69c7d01429c67cce4bda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298470"
---
# <a name="linker-tools-warning-lnk4022"></a>Предупреждение средств компоновщика LNK4022

не удается найти уникальное соответствие для символа «символ»

ССЫЛКА или LIB обнаружено несколько соответствует для упрощенного заданного символа и не может разрешить неоднозначность. Создается выходной файл не (.exe, .dll, .exp или .lib). Это предупреждение сопровождается одно предупреждение [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) для каждого Дублировать символ после чего возникает неустранимая ошибка [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).

Чтобы устранить это предупреждение, укажите символ в декорированном виде. Запустите [DUMPBIN](../../build/reference/dumpbin-options.md) на объект для просмотра внутренних имен.