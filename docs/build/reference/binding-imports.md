---
title: Привязка Imports
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 6ee9d9cc180e77d817b7b52baa1a6eb5209a8365
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486350"
---
# <a name="binding-imports"></a>Привязка Imports

Поведение компоновщика по умолчанию является создание связанной таблицы адресов импорта для библиотеки DLL, загружаемых с задержкой. Если библиотека DLL привязана, вспомогательная функция будет пытаться использовать данные привязки вместо вызова метода **GetProcAddress** на каждого из импортов, на который указывает ссылка. Если метка времени или предпочтительный адрес не совпадают с загружаемой библиотеки DLL, вспомогательная функция предполагает связанная таблица адресов импорта устарела и будет продолжена, как если бы он не существует.

Если не требуется привязать импорты, загружаемые с задержкой DLL, указание [/delay](../../build/reference/delay-delay-load-import-settings.md): nobind в командной строке компоновщика предотвратит связанная таблица адресов импорта созданный и занимать много места в файле образа.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)