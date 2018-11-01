---
title: /APPCONTAINER
ms.date: 11/04/2016
f1_keywords:
- /APPCONTAINER
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
ms.openlocfilehash: 0805393990070a10caed8208138e31ab9084bdf0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482559"
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
[Что такое универсальное приложение Windows?](/windows/uwp/get-started/universal-application-platform-guide)