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
ms.openlocfilehash: ad451f5900841abe3f0fe10ae99fa0183e14e5c5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412601"
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
