---
title: Ошибки позиции файла
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: f8c1d5dfc6a599533ce8c1dcfa624d2595779f2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554613"
---
# <a name="file-position-errors"></a>Ошибки позиции файла

**ANSI 4.9.9.1, 4.9.9.4** Значение, задаваемое макросу `errno` функциями `fgetpos` и `ftell` при ошибке

В случае сбоя функции `fgetpos` или `ftell` для макроса `errno` задается значение константы `EINVAL` из манифеста, если недопустима позиция, или значение `EBADF`, если недопустим номер файла. Эти константы определены в файле ERRNO.H.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
