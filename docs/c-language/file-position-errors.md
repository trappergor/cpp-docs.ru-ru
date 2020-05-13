---
title: Ошибки позиции файла
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: 3d581d86d6f08eee564feb6373a623512085ccca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233661"
---
# <a name="file-position-errors"></a>Ошибки позиции файла

**ANSI 4.9.9.1, 4.9.9.4** Значение, задаваемое макросу `errno` функциями `fgetpos` и `ftell` при ошибке

В случае сбоя функции `fgetpos` или `ftell` для макроса `errno` задается значение константы `EINVAL` из манифеста, если недопустима позиция, или значение `EBADF`, если недопустим номер файла. Эти константы определены в файле ERRNO.H.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
