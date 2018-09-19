---
title: Неустранимая ошибка NMAKE U1051 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3d3a14b75a30aa22bcc9faafb97a218051bb080
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045020"
---
# <a name="nmake-fatal-error-u1051"></a>Неустранимая ошибка NMAKE U1051

Недостаточно памяти

NMAKE не хватило памяти, включая виртуальной памяти, поскольку файл makefile слишком больших или сложных.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Освободите место на диске.

1. Увеличьте размер файла подкачки Windows NT или файл подкачки Windows.

1. Часть файла makefile используется, если только разделить файл makefile в отдельные файлы или использовать **! Если** директивы для ограничения объема обработки NMAKE предварительной обработки. **! Если** относятся **! Если**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! ELSE** `IFDEF`, и **! ELSE** `IFNDEF`.