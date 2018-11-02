---
title: Ошибка средств компоновщика LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 69ac20522aebb7391319c0de210e06b305f3fd0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461260"
---
# <a name="linker-tools-error-lnk1188"></a>Ошибка средств компоновщика LNK1188

BADFIXUPSECTION:: целевой объект недопустимая адресная привязка «символ»; Возможные раздел нулевой длины

Во время компоновки VxD целевого объекта перемещения не имеет раздел. С помощью LINK386 (устаревшая версия), возможно, запись OMF GROUP (созданный с помощью директивы MASM GROUP) был использован для объединения, секция нулевой длины с другого раздела ненулевой длины. Формат COFF не поддерживает директивы GROUP и разделы нулевой длины. Эта ошибка может возникать, когда ссылка автоматически преобразует такого типа объектов OMF в формат COFF.