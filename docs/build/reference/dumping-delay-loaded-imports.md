---
title: Сохранение отложенно загружаемых импортированных элементов
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: 782da0d29024a8308de0bb4d00656b850629c8ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444165"
---
# <a name="dumping-delay-loaded-imports"></a>Сохранение отложенно загружаемых импортированных элементов

Импорты, загружаемые с задержкой могут быть записаны с помощью [dumpbin/Imports](../../build/reference/imports-dumpbin.md) и отображаются с информацией, немного отличается от обычных импортируемых элементов. Они находятся в отдельном разделе/Imports дамп и явно помечены как импорты, загружаемые с задержкой. Есть ли выгрузить сведений, представленных на рисунке, который указан. Если присутствует информация о привязке, метка времени и даты нужной динамической Библиотеки указаны вместе с связанные адреса импорты.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)