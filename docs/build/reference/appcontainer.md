---
title: -APPCONTAINER | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /APPCONTAINER
dev_langs:
- C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d8e19724183963329b959286a996b4f21d18b4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709187"
---
# <a name="appcontainer"></a>/APPCONTAINER

Помечает исполняемый файл, который должен выполняться в контейнере приложения — например, Microsoft Store или универсальной Windows приложение.

```

/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Примечания

Исполняемый файл, для которого задан параметр **/APPCONTAINER** , может выполняться только в контейнере приложения, то есть в среде изоляции процессов, которая была введена в Windows 8. Для приложений Microsoft Store и универсальной Windows этот параметр должен быть установлен.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)<br/>
[Что такое приложение универсальной Windows?](/windows/uwp/get-started/universal-application-platform-guide)