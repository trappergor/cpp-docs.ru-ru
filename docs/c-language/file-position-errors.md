---
title: Ошибки положения в файле | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8def11317548bfd6e70badab4563891c1b6f864d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031925"
---
# <a name="file-position-errors"></a>Ошибки позиции файла

**ANSI 4.9.9.1, 4.9.9.4** Значение, задаваемое макросу `errno` функциями `fgetpos` и `ftell` при ошибке

В случае сбоя функции `fgetpos` или `ftell` для макроса `errno` задается значение константы `EINVAL` из манифеста, если недопустима позиция, или значение `EBADF`, если недопустим номер файла. Эти константы определены в файле ERRNO.H.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
