---
title: Совместное использование констант | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs:
- C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05226ffcc5a10785391969f8162a76034efc4d92
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097311"
---
# <a name="sharing-constants"></a>Совместное использование констант

Константы для режимов общего доступа к файлам.

## <a name="syntax"></a>Синтаксис

```

#include <share.h>

```

## <a name="remarks"></a>Примечания

Аргумент *shflag* определяет режим общего доступа и состоит из одной или нескольких констант манифеста. Их можно использовать в сочетании с аргументами *oflag* (см. [Константы файлов](../c-runtime-library/file-constants.md)).

В следующей таблице перечислены константы и их смысловые значения:

|Константа|Значение|
|--------------|-------------|
|`_SH_DENYRW`|Запрещает доступ к файлу для чтения и записи|
|`_SH_DENYWR`|Запрещает доступ к файлу для записи|
|`_SH_DENYRD`|Запрещает доступ к файлу для чтения|
|`_SH_DENYNO`|Разрешает доступ для чтения и записи|
|`_SH_SECURE`|Устанавливает безопасный режим (совместный доступ для чтения, монопольный доступ для записи)|

## <a name="see-also"></a>См. также

[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)