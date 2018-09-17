---
title: Сохранение отложенно загружаемых импортированных элементов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29f2faecb29da93729b0be0f40c00c18b82f6344
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720880"
---
# <a name="dumping-delay-loaded-imports"></a>Сохранение отложенно загружаемых импортированных элементов

Импорты, загружаемые с задержкой могут быть записаны с помощью [dumpbin/Imports](../../build/reference/imports-dumpbin.md) и отображаются с информацией, немного отличается от обычных импортируемых элементов. Они находятся в отдельном разделе/Imports дамп и явно помечены как импорты, загружаемые с задержкой. Есть ли выгрузить сведений, представленных на рисунке, который указан. Если присутствует информация о привязке, метка времени и даты нужной динамической Библиотеки указаны вместе с связанные адреса импорты.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)