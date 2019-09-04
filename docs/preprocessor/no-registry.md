---
title: no_registry, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: 7c81cc2f570cb9ac4e977dac6d55cb69e491d3b2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220721"
---
# <a name="no_registry-import-attribute"></a>no_registry, атрибут импорта

**no_registry** указывает компилятору не выполнять поиск в реестре библиотек типов, импортированных с помощью `#import`.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **no_registry**

### <a name="parameters"></a>Параметры

*Библиотека типов*\
Библиотека типов.

## <a name="remarks"></a>Примечания

Если библиотека типов, на которую указывает ссылка, не найдена в каталогах включения, компиляция завершается сбоем, даже если библиотека типов находится в реестре.  **no_registry** распространяется на другие библиотеки типов, которые неявно импортируются `auto_search`с помощью.

Компилятор не ищет в реестре библиотеки типов, которые указаны по имени файла и передаются непосредственно `#import`в.

Если `auto_search` указан параметр, дополнительные `#import` директивы создаются с помощью параметра **no_registry** начального `#import`значения. Если начальная `#import` директивабыла `auto_search`no_registry, создается `#import` также **no_registry**.

**no_registry** полезен, если требуется импортировать библиотеки типов с перекрестными ссылками. Компилятор не находит более раннюю версию файла в реестре. **no_registry** также полезен, если библиотека типов не зарегистрирована.

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
