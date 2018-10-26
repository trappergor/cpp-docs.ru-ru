---
title: Дата и время по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- time, default
- dates, default for _DATE and _TIME
ms.assetid: 2a00a772-94f9-4513-a76b-63441456c1e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61f512d82ee33e0b900d61ff4a90c18336f88a16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020664"
---
# <a name="default-date-and-time"></a>Дата и время по умолчанию

**ANSI 3.8.8**. Определения для `__DATE__` и `__TIME__`, когда недоступно преобразование даты и времени соответственно.

Если операционная система не предоставляет преобразование даты и времени, _DATE`__DATE__` и _TIME`__TIME__` по умолчанию получают значения `May 03 1957` и `17:00:00`.

## <a name="see-also"></a>См. также

[Директивы предварительной обработки](../c-language/preprocessing-directives.md)