---
title: Ограничения обработчиков исключений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29a462f83bff3bab158e9bcf9fa7947efb56a79b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074478"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений

Главное ограничение на использование обработчиков исключений в коде в том, что нельзя использовать **goto** инструкцию, чтобы перейти к **__try** блока инструкций. Входить в этот блок необходимо только через обычный поток управления. Вы можете переходить из **__try** инструкции блокировать и создавать вложенные обработчики исключений, как захотите.

## <a name="see-also"></a>См. также

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)