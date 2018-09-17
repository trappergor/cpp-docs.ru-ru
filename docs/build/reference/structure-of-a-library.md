---
title: Структура библиотеки | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03c2c66d45ee415ddc4f3ba27b6a100c5e2ec1dc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702108"
---
# <a name="structure-of-a-library"></a>Структура библиотеки

Библиотека содержит объекты COFF. Объекты в библиотеке содержат функции и данные, которые могут быть внешние ссылки другими объектами в программе. Объект в библиотеке, иногда называется члена библиотеки.

Дополнительные сведения о содержимом библиотеки можно получить, запустив средство (программа DUMPBIN) с параметром/LINKERMEMBER. Дополнительные сведения об этом параметре см. в разделе [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md).

## <a name="see-also"></a>См. также

[Общие сведения о LIB](../../build/reference/overview-of-lib.md)