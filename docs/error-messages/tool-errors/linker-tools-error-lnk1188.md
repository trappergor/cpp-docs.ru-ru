---
title: Ошибка средств компоновщика LNK1188 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36b31590d94d809c16ed64d16071db0919f60238
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098944"
---
# <a name="linker-tools-error-lnk1188"></a>Ошибка средств компоновщика LNK1188

BADFIXUPSECTION:: целевой объект недопустимая адресная привязка «символ»; Возможные раздел нулевой длины

Во время компоновки VxD целевого объекта перемещения не имеет раздел. С помощью LINK386 (устаревшая версия), возможно, запись OMF GROUP (созданный с помощью директивы MASM GROUP) был использован для объединения, секция нулевой длины с другого раздела ненулевой длины. Формат COFF не поддерживает директивы GROUP и разделы нулевой длины. Эта ошибка может возникать, когда ссылка автоматически преобразует такого типа объектов OMF в формат COFF.