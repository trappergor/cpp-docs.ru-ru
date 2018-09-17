---
title: Привязка Imports | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 551028999d11379c06d3319f01e882a33ad57936
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705202"
---
# <a name="binding-imports"></a>Привязка Imports

Поведение компоновщика по умолчанию является создание связанной таблицы адресов импорта для библиотеки DLL, загружаемых с задержкой. Если библиотека DLL привязана, вспомогательная функция будет пытаться использовать данные привязки вместо вызова метода **GetProcAddress** на каждого из импортов, на который указывает ссылка. Если метка времени или предпочтительный адрес не совпадают с загружаемой библиотеки DLL, вспомогательная функция предполагает связанная таблица адресов импорта устарела и будет продолжена, как если бы он не существует.

Если не требуется привязать импорты, загружаемые с задержкой DLL, указание [/delay](../../build/reference/delay-delay-load-import-settings.md): nobind в командной строке компоновщика предотвратит связанная таблица адресов импорта созданный и занимать много места в файле образа.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)