---
title: Привязка Imports
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 90af3af7e71928b18c77c0d21ff6a30c4561e251
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415244"
---
# <a name="binding-imports"></a>Привязка Imports

Поведение компоновщика по умолчанию является создание связанной таблицы адресов импорта для библиотеки DLL, загружаемых с задержкой. Если библиотека DLL привязана, вспомогательная функция будет пытаться использовать данные привязки вместо вызова метода **GetProcAddress** на каждого из импортов, на который указывает ссылка. Если метка времени или предпочтительный адрес не совпадают с загружаемой библиотеки DLL, вспомогательная функция предполагает связанная таблица адресов импорта устарела и будет продолжена, как если бы он не существует.

Если не требуется привязать импорты, загружаемые с задержкой DLL, указание [/delay](../../build/reference/delay-delay-load-import-settings.md): nobind в командной строке компоновщика предотвратит связанная таблица адресов импорта созданный и занимать много места в файле образа.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)
